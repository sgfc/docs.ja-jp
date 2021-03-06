---
title: '.NET Framework 4.7、4.6、4.5 移行ガイド '
ms.custom: updateeachrelease
ms.date: 04/10/2018
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8ef6d73aa6cd044cf6808878bf6142a735d015c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391250"
---
# <a name="migration-guide-to-the-net-framework-47-46-and-45"></a>.NET Framework 4.7、4.6、4.5 移行ガイド 
旧バージョンの .NET Framework を使用してアプリを作成した場合、通常は .NET Framework 4.5 とそのポイント リリース (4.5.1 と 4.5.2)、.NET Framework 4.6 とそのポイント リリース (4.6.1 と 4.6.2)、または .NET Framework 4.7 とそのポイント リリース (4.7.1 および 4.7.2) へ簡単にアップグレードできます。 Visual Studio でプロジェクトを開きます。 プロジェクトが旧バージョンの Visual Studio で作成されている場合は、**[Project Compatibility]\(プロジェクト互換性\)** ダイアログ ボックスが自動的に開きます。 Visual Studio におけるプロジェクトのアップグレードの詳細については、「[Visual Studio プロジェクトのポート、移行、アップグレード](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)」と「[Visual Studio 2017 の対象プラットフォームと互換性](/visualstudio/productinfo/vs2017-compatibility-vs)」を参照してください。  
  
 ただし、.NET Framework で行われたいくつかの変更により、コードを変更する必要があります。 .NET Framework 4.5 とそのポイント リリース、.NET Framework 4.6 とそのポイント リリース、または .NET Framework 4.7 とそのポイント リリースの新しい機能を利用することもできます。 .NET Framework の新しいバージョンに対応するためのアプリに対するこの種の変更は、一般に*移行*と呼ばれます。 アプリを移行する必要がない場合、アプリは再コンパイルなしで .NET Framework 4.5 またはそれ以降のバージョンで実行できます。  
  
## <a name="migration-resources"></a>移行のためのリソース  
 アプリを .NET Framework の旧バージョンからバージョン 4.5、4.5.1、4.5.2、4.6、4.6.1、4.6.2、4.7、4.7.1、または 4.7.2 に移行する前に、次のドキュメントを確認してください。  
  
-   [バージョンおよび依存関係](../../../docs/framework/migration-guide/versions-and-dependencies.md)に関するページで、.NET Framework の各バージョンの基になる CLR バージョンの詳細と、アプリを正しくターゲットするためのガイドラインを確認してください。  
  
-   [アプリケーションの互換性](../../../docs/framework/migration-guide/application-compatibility.md)に関するページで、アプリに影響を与える可能性のあるランタイムの変更と再ターゲットの変更、およびそれらの処理方法について確認してください。  
  
-   [クラス ライブラリの互換性のために残されている機能](../../../docs/framework/whats-new/whats-obsolete.md)に関するページで、コード内の互換性のために残されている型またはメンバーと、推奨される代替の型またはメンバーを確認してください。  
  
-   [新機能](../../../docs/framework/whats-new/index.md)に関するページで、アプリに追加できる可能性のある新機能の説明を確認してください。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの互換性](../../../docs/framework/migration-guide/application-compatibility.md)  
 [.NET Framework 1.1 からの移行](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)  
 [バージョンの互換性](../../../docs/framework/migration-guide/version-compatibility.md)  
 [バージョンおよび依存関係](../../../docs/framework/migration-guide/versions-and-dependencies.md)  
 [方法: .NET Framework 4 または 4.5 をサポートするアプリを構成する](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)  
 [新機能](../../../docs/framework/whats-new/index.md)  
 [クラス ライブラリの互換性のために残されている機能](../../../docs/framework/whats-new/whats-obsolete.md)  
 [.NET Framework のバージョンとアセンブリ情報](http://go.microsoft.com/fwlink/?LinkId=201701)  
 [Microsoft .NET Framework のサポート ライフサイクル ポリシー](http://go.microsoft.com/fwlink/?LinkId=196607) [.NET framework 4 の移行に関する問題](net-framework-4-migration-issues.md)
