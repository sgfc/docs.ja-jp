---
title: "ホスト インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a3cad92c204fa10f72d7a9a61460f1234206cb39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-interfaces"></a><span data-ttu-id="b0e33-102">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0e33-102">Hosting Interfaces</span></span>
<span data-ttu-id="b0e33-103">このセクションの内容がアンマネージ インターフェイスについて説明しますホストを使用して、共通言語ランタイム (CLR) をアプリケーションに統合します。</span><span class="sxs-lookup"><span data-stu-id="b0e33-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="b0e33-104">.NET Framework version 2.0 のホスト インターフェイスは、.NET Framework version 1.0 および 1.1 インターフェイスに優先します。</span><span class="sxs-lookup"><span data-stu-id="b0e33-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="b0e33-105">インターフェイスの 2 つのセット間に大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="b0e33-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="b0e33-106">両者を混在させると、予期しない動作が発生する可能性があります、お勧めできません。</span><span class="sxs-lookup"><span data-stu-id="b0e33-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="b0e33-107">.NET Framework バージョン 3.0 および 3.5 は .NET Framework version 2.0 のホスト インターフェイスを使用し、ホスティング機能を導入していません。</span><span class="sxs-lookup"><span data-stu-id="b0e33-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="b0e33-108">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]ホスト インターフェイスは、.NET Framework 2.0 インターフェイスをよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b0e33-108">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b0e33-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b0e33-109">In This Section</span></span>  
 [<span data-ttu-id="b0e33-110">サポートされなくなった CLR ホスト インターフェイスおよびコクラス</span><span class="sxs-lookup"><span data-stu-id="b0e33-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="b0e33-111">.NET Framework のバージョン 1.0 および 1.1 で導入されたホスト インターフェイスをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b0e33-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="b0e33-112">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0e33-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="b0e33-113">.NET Framework version 2.0 で導入されたホスト インターフェイスをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b0e33-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="b0e33-114">CLR ホスト インターフェイスが 4 と 4.5 の .NET Framework の追加</span><span class="sxs-lookup"><span data-stu-id="b0e33-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="b0e33-115">導入されたホスティング インターフェイスについて説明します、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b0e33-115">Describes the hosting interfaces introduced in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b0e33-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0e33-116">Related Sections</span></span>  
 [<span data-ttu-id="b0e33-117">ホスト コクラス</span><span class="sxs-lookup"><span data-stu-id="b0e33-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="b0e33-118">推奨されなくなった CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="b0e33-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="b0e33-119">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="b0e33-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="b0e33-120">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="b0e33-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="b0e33-121">ホスティング</span><span class="sxs-lookup"><span data-stu-id="b0e33-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 [<span data-ttu-id="b0e33-122">ランタイム ホスト</span><span class="sxs-lookup"><span data-stu-id="b0e33-122">Runtime Hosts</span></span>](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)