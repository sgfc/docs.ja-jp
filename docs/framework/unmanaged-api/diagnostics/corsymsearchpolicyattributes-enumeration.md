---
title: "CorSymSearchPolicyAttributes 列挙体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymSearchPolicyAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymSearchPolicyAttributes
helpviewer_keywords: CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 016378de8d4ba4b6f16f7e7b91b6427f73c9687d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="d8f79-102">CorSymSearchPolicyAttributes 列挙体</span><span class="sxs-lookup"><span data-stu-id="d8f79-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="d8f79-103">シンボル リーダーの検索を実行するときに使用されるポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8f79-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="d8f79-104">これらの定数がによって使用される、 [isymunmanagedbinder 2::getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)と[isymunmanagedbinder 3::getreaderfromcallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="d8f79-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d8f79-105">信頼できないソースからプログラム データベース (PDB) ファイルを開く、セキュリティ上のリスクを勧めします。</span><span class="sxs-lookup"><span data-stu-id="d8f79-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8f79-106">構文</span><span class="sxs-lookup"><span data-stu-id="d8f79-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="d8f79-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="d8f79-107">Members</span></span>  
  
|<span data-ttu-id="d8f79-108">メンバー</span><span class="sxs-lookup"><span data-stu-id="d8f79-108">Member</span></span>|<span data-ttu-id="d8f79-109">説明</span><span class="sxs-lookup"><span data-stu-id="d8f79-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="d8f79-110">シンボル検索パスのレジストリを照会します。</span><span class="sxs-lookup"><span data-stu-id="d8f79-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="d8f79-111">シンボル サーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d8f79-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="d8f79-112">デバッグ ディレクトリで指定されたパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="d8f79-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="d8f79-113">.Exe ファイルのある場所に pdb ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="d8f79-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8f79-114">要件</span><span class="sxs-lookup"><span data-stu-id="d8f79-114">Requirements</span></span>  
 <span data-ttu-id="d8f79-115">**ヘッダー:** CorSym.idl、CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d8f79-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f79-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8f79-116">See Also</span></span>  
 [<span data-ttu-id="d8f79-117">シンボル ストア診断列挙体</span><span class="sxs-lookup"><span data-stu-id="d8f79-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)