---
title: "IGCHost::GetStats メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c8db4f854b73d04e7260457c978a7a644677559
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="4094e-102">IGCHost::GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="4094e-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="4094e-103">ガベージ コレクション システムの現在の状態の統計情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="4094e-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4094e-104">構文</span><span class="sxs-lookup"><span data-stu-id="4094e-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4094e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4094e-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="4094e-106">[入力、出力].ポインター、 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)ガベージ コレクション システムの現在の状態の統計情報を格納する構造体。</span><span class="sxs-lookup"><span data-stu-id="4094e-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4094e-107">コメント</span><span class="sxs-lookup"><span data-stu-id="4094e-107">Remarks</span></span>  
 <span data-ttu-id="4094e-108">統計は、スマート割り当てシステムによってガベージ コレクション システムの動作をするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="4094e-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="4094e-109">たとえば、割り当てシステム可能性がありますを判断より多くのメモリを追加またはコレクションを強制的に必要な統計情報を確認した後。</span><span class="sxs-lookup"><span data-stu-id="4094e-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4094e-110">要件</span><span class="sxs-lookup"><span data-stu-id="4094e-110">Requirements</span></span>  
 <span data-ttu-id="4094e-111">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="4094e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4094e-112">**ヘッダー:** GCHost.idl、GCHost.h</span><span class="sxs-lookup"><span data-stu-id="4094e-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="4094e-113">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="4094e-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4094e-114">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4094e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4094e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4094e-115">See Also</span></span>  
 [<span data-ttu-id="4094e-116">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4094e-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)