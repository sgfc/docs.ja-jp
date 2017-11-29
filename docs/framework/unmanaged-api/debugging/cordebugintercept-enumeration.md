---
title: "CorDebugIntercept 列挙型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugIntercept
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugIntercept
helpviewer_keywords: CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7d34b5f1bdff7a7089d780645b91503a8464849
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="3da2f-102">CorDebugIntercept 列挙型</span><span class="sxs-lookup"><span data-stu-id="3da2f-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="3da2f-103">インターセプト (ステップ イン) できるコードの型を示します。</span><span class="sxs-lookup"><span data-stu-id="3da2f-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da2f-104">構文</span><span class="sxs-lookup"><span data-stu-id="3da2f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="3da2f-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3da2f-105">Members</span></span>  
  
|<span data-ttu-id="3da2f-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3da2f-106">Member</span></span>|<span data-ttu-id="3da2f-107">説明</span><span class="sxs-lookup"><span data-stu-id="3da2f-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="3da2f-108">インターセプトできるコードはありません。</span><span class="sxs-lookup"><span data-stu-id="3da2f-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="3da2f-109">コンストラクターをインターセプトできます。</span><span class="sxs-lookup"><span data-stu-id="3da2f-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="3da2f-110">例外フィルターをインターセプトできます。</span><span class="sxs-lookup"><span data-stu-id="3da2f-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="3da2f-111">セキュリティを適用するコードをインターセプトできます。</span><span class="sxs-lookup"><span data-stu-id="3da2f-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="3da2f-112">コンテキスト ポリシーをインターセプトできます。</span><span class="sxs-lookup"><span data-stu-id="3da2f-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="3da2f-113">使用しません。</span><span class="sxs-lookup"><span data-stu-id="3da2f-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="3da2f-114">すべてのコードをインターセプトできます。</span><span class="sxs-lookup"><span data-stu-id="3da2f-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3da2f-115">コメント</span><span class="sxs-lookup"><span data-stu-id="3da2f-115">Remarks</span></span>  
 <span data-ttu-id="3da2f-116">使用して、 [icordebugstepper::setinterceptmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)インターセプトできるコードの型を構築する方法です。</span><span class="sxs-lookup"><span data-stu-id="3da2f-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3da2f-117">要件</span><span class="sxs-lookup"><span data-stu-id="3da2f-117">Requirements</span></span>  
 <span data-ttu-id="3da2f-118">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="3da2f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3da2f-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3da2f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3da2f-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3da2f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3da2f-121">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3da2f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da2f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3da2f-122">See Also</span></span>  
 [<span data-ttu-id="3da2f-123">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="3da2f-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)