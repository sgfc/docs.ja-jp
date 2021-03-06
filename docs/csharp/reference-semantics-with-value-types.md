---
title: 値の型による参照セマンティクス
description: 構造のコピーを安全に最小限に抑える言語機能を理解する
ms.date: 11/10/2017
ms.custom: mvc
ms.openlocfilehash: 0646a7fbc01ed76883fb6b16ce04006049ef054a
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566281"
---
# <a name="reference-semantics-with-value-types"></a>値の型による参照セマンティクス

値の型を利用する利点は、多くの場合にヒープ割り当てが回避されることにあります。
欠点は、値でコピーされるということです。 このトレードオフは、大量のデータを操作するアルゴリズムの最適化を難しくします。 C# 7.2 の新しい言語機能は、値の型による参照渡しセマンティクスを可能にするメカニズムを提供します。 これらの機能を賢く使って、割り当てとコピー操作の両方を最小限に抑えます。 この記事では、これらの新しい機能について説明します。

この記事にあるサンプル コードの多くは、C# 7.2 で追加された機能を示すものです。 そのような機能を使用するには、C# 7.2 以降を使用するようにプロジェクトを構成する必要があります。 言語バージョンを設定する方法の詳細については、[言語バージョンの構成](language-reference/configure-language-version.md)に関する記事を参照してください。

## <a name="passing-arguments-by-readonly-reference"></a>引数の読み取り専用参照渡し

C# 7.2 では、引数を参照渡しするために既存の `ref` キーワードと `out` キーワードを補完する `in` キーワードが追加されています。 `in` キーワードは、引数を参照で渡すことを指定しますが、呼び出されたメソッドは値を変更しません。 

この追加によって、設計の意図を表すためのボキャブラリが完全に与えられます。 メソッド シグネチャで次の修飾子のいずれも指定しないのであれば、呼び出されたメソッドに渡されるとき、値の型がコピーされます。 これらの修飾子のいずれも、値の型が参照で渡され、コピーが回避されます。 修飾子はそれぞれ、異なる意図を表します。

- `out`: このメソッドは、このパラメーターとして使用される引数の値を設定します。
- `ref`: このメソッドは、このパラメーターとして使用される引数の値を設定することがあります。
- `in`: このメソッドは、このパラメーターとして使用される引数の値を変更しません。

`in` 修飾子を追加し、参照で引数を渡し、参照で引数を渡して不必要なコピーを回避する設計の意図を宣言します。 その引数として使用されるオブジェクトの変更は意図しません。 次のコードは、3D 空間の 2 点間の距離を計算するメソッドの例です。 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

引数は 2 つの構造で、それぞれに 3 つの倍精度浮動小数点型が含まれます。 倍精度浮動小数点型は 8 バイトです。そのため、各引数は 24 バイトになります。 `in` 修飾子を指定することで、コンピューターのアーキテクチャに基づき、4 バイトまたは 8 バイトの参照をそれらの引数に渡します。 サイズの差はわずかですが、アプリケーションにおいて、繰り返しの多いループでさまざまな値でこのメソッドを呼び出すと、すぐに差が膨れ上がります。
 
`in` 修飾子は、その他の面でも `out` と `ref` を補完します。 `in`、`out`、または `ref` の存在のみが異なるメソッドのオーバーロードは作成できません。 これらの新しいルールは、`out` パラメーターと `ref` パラメーターに常に定義されていた同じ動作を拡張します。

`in` 修飾子は、メソッド、デリケート、ラムダ、ローカル関数、インデクサー、演算子など、パラメーターを受け取るあらゆるメンバーに適用されることがあります。

`ref` 引数や `out` 引数とは異なり、`in` パラメーターの引数にリテラル値か定数を使用できます。 また、`ref` パラメーターや `out` パラメーターとは異なり、呼び出しサイトで `in` 修飾子を適用する必要はありません。 次のコードは、`CalculateDistance` メソッドを呼び出す 2 つの例です。 最初のメソッドでは、参照で渡される 2 つのローカル変数が使用されます。 2 つ目のメソッドには、メソッド呼び出しの一部として作成される一時的な変数が含まれます。 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

コンパイラにおいて、`in` 引数の読み取り専用の性質を強制する方法がいくつかあります。  まず、呼び出されたメソッドは `in` パラメーターに直接割り当てできません。 値が `struct` 型の場合、`in` パラメーターのどのフィールドにも直接割り当てできません。 また、`ref` または `out` 修飾子を使用するメソッドに `in` パラメーターを渡すことができません。
これらの規則は、`in` パラメーターのすべてのフィールドに適用されます (ただし、フィールドが `struct` 型でパラメーターも `struct` 型の場合)。 実際、これらの規則は、メンバー アクセスのすべてのレベルで型が `structs` であれば、複数層のメンバー アクセスに適用されます。 コンパイラは `struct` 型を `in` 引数として渡し、その `struct` メンバーが他のメソッドへの引数として使用される場合は読み取り専用変数になるよう強制します。

`in` パラメーターを使用することで、コピーを作成することの潜在的なパフォーマンス コストを回避できます。 メソッド呼び出しのセマンティクスは変更されません。 そのため、呼び出しサイトで `in` 修飾子を指定する必要はありません。 ただし、呼び出しサイトで `in` 修飾子を省略すると、次の理由で、引数のコピーを作成することが許可されていることがコンパイラに通知されます。

- 暗黙的な変換はあるが、引数の型からパラメーターの型への ID 変換がない。
- 引数は式だが、既知のストレージ変数がない。
- `in` の有無によって異なるオーバーロードが存在する。 この場合は、値渡しオーバーロードの方がより適しています。

これらの規則は、既存のコードを読み取り専用の参照引数を使用するように更新するときに役立ちます。 呼び出されるメソッド内で、値渡しパラメーターを使用する任意のインスタンス メソッドを呼び出すことができます。 それらのインスタンスで、`in` パラメーターのコピーが作成されます。 コンパイラは `in` パラメーターに一時的な変数を作成できるため、`in` パラメーターに既定値を指定することもできます。 次のコードでは、2 つ目の点の既定値として原点 (点 0,0) を指定します。

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

コンパイラに読み取り専用引数の参照渡しを強制するには、次のコードに示すように、呼び出しサイトで引数に `in` 修飾子を指定します。

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#ExplicitInArgument "Specifying an In argument")]

この動作により、パフォーマンスの向上が可能な大規模なコードベースで、徐々に `in` パラメーターを採用しやすくなります。 最初に、メソッド シグネチャに `in` 修飾子を追加します。 その後、呼び出しサイトで `in` 修飾子を追加し、`readonly struct` 型を作成して、コンパイラに他の場所で `in` パラメーターの防御用コピーを作成しないようにすることができます。

`in` パラメーターの指定は、参照型または数値と併用することもできます。 ただし、いずれの場合も、利点があるとしてもわずかです。

## <a name="ref-readonly-returns"></a>`ref readonly` 戻り値

参照で値の型を返すが、呼び出し元にはその値の変更を禁止する場合もあります。 `ref readonly` 修飾子を使用し、その設計の意図を表します。 既存のデータへの参照を返すが、変更を許可しないことを閲覧者に通知します。 

コンパイラは、呼び出し元は参照を変更できないことを強制します。 値を直接割り当てようとすると、コンパイル時エラーが生成されます。 ただし、メンバー メソッドによって構造体の状態が変更されるか、コンパイラは認識できません。
オブジェクトが変更されないように、コンパイラはコピーを作成し、そのコピーを利用してメンバー参照を呼び出します。 変更されるとすれば、その防御用のコピーに行われます。 

`Point3D` を使用するライブラリは、多くの場合、コード全体で原点を使用する可能性が高いです。 インスタンスごとに、スタックに新しいオブジェクトが作成されます。 定数を作成し、それを参照で返すことには利点がある場合があります。 ただし、内部の記憶域に参照を返す場合、参照される記憶域を呼び出し元が変更できないように強制することが勧められます。 次のコードでは、原点を指定する `Point3D` に `readonly ref` を返す読み取り専用プロパティが定義されます。

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

参照読み取り専用戻り値のコピーの作成は簡単です。`ref readonly` 修飾子で宣言されない変数にそれを割り当てるだけです。 割り当ての一環としてオブジェクトをコピーするコードがコンパイラによって生成されます。 

変数を `ref readonly return` に割り当てるとき、`ref readonly` 変数か、読み取り専用参照の値渡しコピーを指定できます。

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

先のコードの最初の割り当てでは、`Origin` 定数のコピーが作成され、そのコピーが割り当てられます。 2 つ目は参照を割り当てます。 `readonly` 修飾子は変数の宣言の一部にする必要があります。 それが参照するものは変更できません。 変更を試みると、コンパイル時エラーが発生します。

## <a name="readonly-struct-type"></a>`readonly struct` 型

構造体の高トラフィック利用に `ref readonly` を適用する方法で十分な場合があります。
不変構造体の作成が勧められる場合もあります。 その後、常に読み取り専用参照で渡すことができます。 この方法では、`in` パラメーターとして使用される構造のメソッドにアクセスするときに発生する防御用のコピーが取り除かれます。

これは `readonly struct` 型を作成することで実行できます。 構造体宣言に `readonly` 修飾子を追加できます。 その構造体のすべてのインスタンス メンバーが `readonly` になるようにコンパイラは強制します。`struct` は変更不可能でなければなりません。

`readonly struct` は最適化が他にもあります。 `in` が引数となるあらゆる場所で `readonly struct` 修飾子を使用できます。 また、有効期間がオブジェクトを返すメソッドの範囲を超えるオブジェクトを返すとき、`ref return` として `readonly struct` を返すことができます。

最後に、`readonly struct` のメンバーを呼びだすと、コンパイラは一層効率的なコードを生成します。レシーバーのコピーではなく、`this` 参照が常に、メンバー メソッドに参照で渡される `in` パラメーターになります。 この最適化によって、`readonly struct` の利用時、省略されるコピーが多くなります。 この変更の対象として `Point3D` が勧められます。 次のコードは、更新後の `ReadonlyPoint3D` 構造体を示します。

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a>`ref struct` 型

関連するもう 1 つの言語機能は、スタック割り当てにする必要がある値型を宣言する機能です。 言い換えると、このような型を別のクラスのメンバーとしてヒープ上で作成することはできません。 この機能の第一の動機は <xref:System.Span%601> と関連構造でした。 <xref:System.Span%601> には、そのメンバーの 1 つとしてマネージ ポインターが含まれます。他方はスパンの長さです。 実装は少し異なります。C# の場合、安全ではないコンテキストの外では、マネージ メモリのポインターがサポートされていないためです。 ポインターや長さを変更する記述はアトミックではありません。 つまり、単一のスタック フレームに制約されない場合、<xref:System.Span%601> は範囲外エラーか、その他のタイプ セーフ違反になります。 また、GC ヒープ上にマネージ ポインターを置くと、通常、JIT 時にクラッシュします。

[`stackalloc`](language-reference/keywords/stackalloc.md) で作成したメモリを使用するとき、あるいは相互運用 API からメモリを使用するとき、同様の要件が求められる場合があります。 そのようなニーズには独自の `ref struct` 型を定義できます。 この記事の例では `Span<T>` を利用し、わかりやすくしています。

`ref struct` 宣言によって、この型の構造体はスタック上に置かなければならないことが宣言されます。 言語規則により、この型が安全に使用されます。 `ref struct` として宣言されるその他の型には <xref:System.ReadOnlySpan%601> があります。 

スタック割り当て変数として `ref struct` 型を維持する目的の下、すべての `ref struct` 型にコンパイラが適用する規則がいくつか導入されます。

- `ref struct` はボックス化できません。 `object` 型、`dynamic` 型、またはあらゆるインターフェイス型の変数には、`ref struct` 型を割り当てることができません。
- クラスまたは通常構造体のメンバーとして `ref struct` を宣言することはできません。
- 非同期メソッドでは、`ref struct` 型のローカル変数を宣言できません。 `Task`、`Task<T>`、あるいは Task のような型を返す同期メソッドで宣言できます。
- 反復子で `ref struct` ローカル変数を宣言することはできません。
- ラムダ式またはローカル関数で `ref struct` 変数をキャプチャすることはできません。

これらの制約によって、誤って、マネージ ヒープに昇格させるようなやり方で `ref struct` を使用することがなくなります。

## <a name="readonly-ref-struct-type"></a>`readonly ref struct` 型

構造体を `readonly ref` として宣言すると、`ref struct` と `readonly struct` の制限の利点と制限が組み合わされます。 

次の例は、`readonly ref struct` の宣言を示しています。

```csharp
readonly ref struct ReadOnlyRefPoint2D
{
    public int X { get; }
    public int Y { get; }
    
    public ReadOnlyRefPoint2D(int x, int y) => (X, Y) = (x, y);
}
```

## <a name="conclusions"></a>まとめ

C# 言語の以上の拡張機能は、必要なパフォーマンスの達成にメモリ割り当てが重要となる、パフォーマンス クリティカルなアルゴリズムのために設計されています。 自分が記述するコードではこれらの機能を頻繁に使用することがないかもしれません。 しかしながら、以上の拡張機能は、.NET Framework では、さまざまな場所で採用されています。 これらの機能を利用する API が増えれば、自分で作るアプリケーションのパフォーマンスが改善するでしょう。
