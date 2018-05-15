### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="c52e6-101">タッチ対応システムで System.Windows.Input.PenContext.Disable を呼び出すと ArgumentException がスローされることがある</span><span class="sxs-lookup"><span data-stu-id="c52e6-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c52e6-102">説明</span><span class="sxs-lookup"><span data-stu-id="c52e6-102">Details</span></span>|<span data-ttu-id="c52e6-103">一部の状況では、タッチ対応システムで内部 <strong>System.Windows.Intput.PenContext.Disable</strong> メソッドを呼び出すと、再入に起因して未処理の <code>T:System.ArgumentException</code> がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="c52e6-103">Under some circumstances, calls to the internal <strong>System.Windows.Intput.PenContext.Disable</strong> method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="c52e6-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c52e6-104">Suggestion</span></span>|<span data-ttu-id="c52e6-105">この問題は、.NET Framework 4.7 では対処済みです。</span><span class="sxs-lookup"><span data-stu-id="c52e6-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="c52e6-106">例外を防ぐには、.NET Framework 4.7 以降のバージョンの .NET Framework にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="c52e6-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="c52e6-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="c52e6-107">Scope</span></span>|<span data-ttu-id="c52e6-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="c52e6-108">Edge</span></span>|
|<span data-ttu-id="c52e6-109">Version</span><span class="sxs-lookup"><span data-stu-id="c52e6-109">Version</span></span>|<span data-ttu-id="c52e6-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="c52e6-110">4.6.1</span></span>|
|<span data-ttu-id="c52e6-111">型</span><span class="sxs-lookup"><span data-stu-id="c52e6-111">Type</span></span>|<span data-ttu-id="c52e6-112">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="c52e6-112">Retargeting</span></span>|
