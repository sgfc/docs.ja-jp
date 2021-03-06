---
title: LINQ と ADO.NET
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: 1385b2d9b49a7615810025141e111b7d7bf71eac
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766128"
---
# <a name="linq-and-adonet"></a>LINQ と ADO.NET
現在、多くのビジネス開発者が 2 つ (以上) のプログラミング言語を使用する必要があります: (Visual c# や Visual Basic)、ビジネス ロジックやプレゼンテーション層は高級言語と、データベースとやり取りするクエリ言語 (など[!INCLUDE[tsql](../../../../includes/tsql-md.md)])。 開発者は実質的に複数の言語に精通していることが要求され、開発環境における言語の不整合が生じる原因にもなっています。 たとえば、データ アクセス API を使用してデータベースを照会するアプリケーションでは、クエリは文字列リテラルとして引用符で囲んで指定する必要があります。 コンパイラはこのクエリ文字列を認識できないため、エラー (無効な構文、参照されている列または行が実際に存在するかどうかなど) のチェック機構が働きません。 クエリ パラメーターの型チェックや `IntelliSense` のサポートもありません。  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] により、開発者はアプリケーション コード内でプログラミング言語とクエリ言語を使い分けることなく、セット ベースのクエリを作成できます。 インメモリのデータ構造、XML ドキュメント、SQL データベース、[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] オブジェクトなど、列挙可能な各種データ ソース (つまり、<xref:System.Collections.IEnumerable> インターフェイスを実装するデータ ソース) に対する <xref:System.Data.DataSet> クエリを作成できます。 実装方法には違いがありますが、こうした列挙可能なデータ ソースはすべて同じ構文および言語構造を公開しています。 クエリはプログラミング言語のみで作成できるため、コンパイラによる認識も検証もできない文字列リテラルとしてクエリ言語を記述する必要はありません。 Visual Studio プログラマは、コンパイル時の型チェックや構文は次のチェックを提供することによって生産性を向上させることもできますクエリに統合するプログラミング言語と`IntelliSense`です。 クエリのデバッグやエラーの修正に伴う手間は、これらの機能によって軽減されます。  
  
 SQL テーブルのデータをメモリ内のオブジェクトに転送することは、面倒であるだけでなく間違いの元にもなります。 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] および [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] で実装された [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] プロバイダーは、ソース データを <xref:System.Collections.IEnumerable> ベースのオブジェクト コレクションに変換します。 プログラマからは、クエリの実行時も更新時も常にデータが <xref:System.Collections.IEnumerable> コレクションとして見えます。 これらのコレクションに対するクエリを記述する際には、`IntelliSense` の機能を完全に利用できます。  
  
 ADO.NET [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] には、[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]、[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]、および [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] の 3 つのテクノロジがあります。 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] に対する豊富な最適化されたクエリを提供、<xref:System.Data.DataSet>と[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]SQL Server データベース スキーマを直接クエリすることができ、[!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]クエリを実行することができます、[!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]です。  
  
 次の図は、ADO.NET LINQ テクノロジが、高級プログラミング言語および LINQ 対応のデータ ソースとどのように関係しているかを簡単に表したものです。  
  
 ![LINQ to ADO.NET の概要](../../../../docs/framework/data/adonet/media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 LINQ の言語機能の概要については、次を参照してください。 [LINQ の概要](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)です。 アプリケーションでの LINQ の使用については、次を参照してください。、[ビルド内にありません: LINQ の一般的なプログラミング ガイド](http://msdn.microsoft.com/library/609c7a6b-cbdd-429d-99f3-78d13d3bc049)、LINQ テクノロジを使用する方法についての詳細が含まれています。  
  
 以降のセクションで、[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]、[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]、および [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] について詳しく説明します。  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> は、[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] の基礎である非接続型プログラミング モデルの重要な要素であり幅広く使用されています。 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] により、開発者は、他の多くのデータ ソースで利用できる共通のクエリ作成メカニズムを使用しながら、より高度なクエリ機能を <xref:System.Data.DataSet> に組み込むことができます。 詳細については、「[LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)」を参照してください。  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] は、概念モデルへのマッピングを必要としない開発者にとって有用なツールです。 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] では、[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] プログラミング モデルを既存のデータベース スキーマ上で直接利用できるようになります。 開発者は、データを表現する [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] クラスを、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] を使って生成できます。 こうして生成されたクラスは、概念データ モデルではなく、直接データベースのテーブル、ビュー、ストアド プロシージャ、およびユーザー定義関数にマッピングされます。  
  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] では、開発者が、XML などのデータ ソースに加え、インメモリ コレクションや [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] と同じ <xref:System.Data.DataSet> プログラミング パターンを使用して、ストレージ スキーマに対して直接コードを記述できます。 詳細については、「[LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)」を参照してください。  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 現在、多くのアプリケーションが、リレーショナル データベースを基にして作成されています。 ある時点で、これらのアプリケーションにはリレーショナル形式で表されるデータと対話する必要が生じます。 データベース スキーマはアプリケーションの構築に理想的であるとは限らず、アプリケーションの概念モデルはデータベースの論理モデルと同じではありません。 [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]は、アプリケーションがデータをオブジェクトとして操作するために特定のドメインのデータをモデル化するときに使用できる概念データ モデルです。 参照してください[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)詳細についてはします。  
  
 [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]を介して、リレーショナル データは .NET 環境でオブジェクトとして公開されます。 これにより、[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] の利用に最適なオブジェクト レイヤーが実現されます。開発者は、ビジネス ロジックの構築に使用する言語で、データベースを照会するクエリを作成できます。 この機能は、[!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] と呼ばれます。 LINQ の詳細については、「[LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)  
 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)  
 [統合言語クエリ (LINQ)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [ADO.NET のマネージ プロバイダーと DataSet デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=217917)
