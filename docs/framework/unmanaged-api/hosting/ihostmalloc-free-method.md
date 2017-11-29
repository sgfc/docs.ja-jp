---
title: "IHostMAlloc::Free メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc.Free
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ac361f939a134aa6d2bc8b215c5d447b352466e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="93409-102">IHostMAlloc::Free メソッド</span><span class="sxs-lookup"><span data-stu-id="93409-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="93409-103">使用して割り当てられたメモリを解放、[アロケーション](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)関数。</span><span class="sxs-lookup"><span data-stu-id="93409-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93409-104">構文</span><span class="sxs-lookup"><span data-stu-id="93409-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93409-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="93409-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="93409-106">[in]解放するメモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="93409-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93409-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="93409-107">Return Value</span></span>  
  
|<span data-ttu-id="93409-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="93409-108">HRESULT</span></span>|<span data-ttu-id="93409-109">説明</span><span class="sxs-lookup"><span data-stu-id="93409-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="93409-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="93409-110">S_OK</span></span>|<span data-ttu-id="93409-111">`Free`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="93409-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="93409-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="93409-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="93409-113">共通言語ランタイム (CLR) が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。</span><span class="sxs-lookup"><span data-stu-id="93409-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="93409-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="93409-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="93409-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="93409-115">The call timed out.</span></span>|  
|<span data-ttu-id="93409-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="93409-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="93409-117">呼び出し元は、ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="93409-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="93409-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="93409-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="93409-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="93409-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="93409-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="93409-120">E_FAIL</span></span>|<span data-ttu-id="93409-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="93409-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="93409-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="93409-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="93409-123">メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。</span><span class="sxs-lookup"><span data-stu-id="93409-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="93409-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="93409-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="93409-125">ホストが割り当てられていないメモリを解放しようとしました。</span><span class="sxs-lookup"><span data-stu-id="93409-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93409-126">コメント</span><span class="sxs-lookup"><span data-stu-id="93409-126">Remarks</span></span>  
 <span data-ttu-id="93409-127">場合、`pMem`パラメーターへの呼び出しを使用して、割り当てられていないメモリの領域を指す`Alloc`ホストが HOST_E_INVALIDOPERATION を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="93409-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93409-128">要件</span><span class="sxs-lookup"><span data-stu-id="93409-128">Requirements</span></span>  
 <span data-ttu-id="93409-129">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="93409-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93409-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="93409-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93409-131">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="93409-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93409-132">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93409-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93409-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="93409-133">See Also</span></span>  
 [<span data-ttu-id="93409-134">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="93409-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="93409-135">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="93409-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)