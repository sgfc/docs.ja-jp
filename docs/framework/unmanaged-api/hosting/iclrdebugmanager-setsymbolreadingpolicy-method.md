---
title: "ICLRDebugManager::SetSymbolReadingPolicy メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.SetSymbolReadingPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d116883c39b4400451ede07df83ac77893ce285c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="e637a-102">ICLRDebugManager::SetSymbolReadingPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="e637a-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="e637a-103">プログラム データベース (PDB) ファイルを読み取るためのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="e637a-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="e637a-104">ポリシーは、呼び出し履歴に行番号およびファイルに関する情報が含まれているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e637a-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e637a-105">構文</span><span class="sxs-lookup"><span data-stu-id="e637a-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e637a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e637a-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="e637a-107">[in]メンバー、 [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md)列挙します。</span><span class="sxs-lookup"><span data-stu-id="e637a-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e637a-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e637a-108">Return Value</span></span>  
  
|<span data-ttu-id="e637a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e637a-109">HRESULT</span></span>|<span data-ttu-id="e637a-110">説明</span><span class="sxs-lookup"><span data-stu-id="e637a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e637a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e637a-111">S_OK</span></span>|<span data-ttu-id="e637a-112">`SetSymbolReadingPolicy`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="e637a-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="e637a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e637a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e637a-114">共通言語ランタイム (CLR) が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。</span><span class="sxs-lookup"><span data-stu-id="e637a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e637a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e637a-115">E_FAIL</span></span>|<span data-ttu-id="e637a-116">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e637a-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e637a-117">メソッドには、E_FAIL が返された、後に、CLR はプロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e637a-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e637a-118">メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。</span><span class="sxs-lookup"><span data-stu-id="e637a-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e637a-119">要件</span><span class="sxs-lookup"><span data-stu-id="e637a-119">Requirements</span></span>  
 <span data-ttu-id="e637a-120">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="e637a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e637a-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e637a-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e637a-122">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="e637a-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e637a-123">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e637a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e637a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e637a-124">See Also</span></span>  
 [<span data-ttu-id="e637a-125">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e637a-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)