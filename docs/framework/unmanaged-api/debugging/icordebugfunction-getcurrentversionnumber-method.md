---
title: "ICorDebugFunction::GetCurrentVersionNumber メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetCurrentVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b4e26be7e50f7746caeb793bef6d6dbcfed7eef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="fe1c5-102">ICorDebugFunction::GetCurrentVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="fe1c5-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="fe1c5-103">この ICorDebugFunction オブジェクトによって表される関数に対して行われた最後の編集のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe1c5-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe1c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="fe1c5-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe1c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe1c5-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="fe1c5-106">[out]この関数に対する最後の編集のバージョンの数を表す整数値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe1c5-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe1c5-107">コメント</span><span class="sxs-lookup"><span data-stu-id="fe1c5-107">Remarks</span></span>  
 <span data-ttu-id="fe1c5-108">この関数に対する最後の編集のバージョン番号は、関数自体のバージョン番号より大きい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe1c5-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="fe1c5-109">いずれかを使用して、 [icordebugfunction 2::getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)メソッドまたは[icordebugcode::getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)関数のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe1c5-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe1c5-110">要件</span><span class="sxs-lookup"><span data-stu-id="fe1c5-110">Requirements</span></span>  
 <span data-ttu-id="fe1c5-111">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="fe1c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe1c5-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe1c5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe1c5-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe1c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe1c5-114">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe1c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>