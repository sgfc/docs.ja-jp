---
title: "IApartmentCallback インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: IApartmentCallback
helpviewer_keywords: IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d2f2ea73da2273ff6f0abb725ec3e3fb8ca79ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="32ea2-102">IApartmentCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32ea2-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="32ea2-103">アパートメント内でコールバックを行うためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="32ea2-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="32ea2-104">*アパートメント*が同じスレッド アクセス要件を共有するオブジェクトのプロセス内の論理コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="32ea2-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="32ea2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="32ea2-105">Methods</span></span>  
  
|<span data-ttu-id="32ea2-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="32ea2-106">Method</span></span>|<span data-ttu-id="32ea2-107">説明</span><span class="sxs-lookup"><span data-stu-id="32ea2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="32ea2-108">DoCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="32ea2-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="32ea2-109">アパートメント内で指定された関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="32ea2-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32ea2-110">要件</span><span class="sxs-lookup"><span data-stu-id="32ea2-110">Requirements</span></span>  
 <span data-ttu-id="32ea2-111">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="32ea2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32ea2-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32ea2-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32ea2-113">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="32ea2-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32ea2-114">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32ea2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ea2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="32ea2-115">See Also</span></span>  
 [<span data-ttu-id="32ea2-116">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32ea2-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)