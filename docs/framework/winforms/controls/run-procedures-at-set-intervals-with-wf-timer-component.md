---
title: "方法 : Windows フォームの Timer コンポーネントを使用して一定間隔でプロシージャを実行する | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "例 [Windows フォーム], タイマー"
  - "初期化, Timer コンポーネント"
  - "プロシージャ, 特定の時間間隔"
  - "Timer コンポーネント [Windows フォーム], 初期化"
  - "タイマー, イベントの間隔"
  - "タイマー, Windows ベースの"
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 方法 : Windows フォームの Timer コンポーネントを使用して一定間隔でプロシージャを実行する
ループが完了するまで特定の間隔で実行するプロシージャや、設定した間隔が経過した時点で実行するプロシージャを作成することがあるかもしれません。  <xref:System.Windows.Forms.Timer> コンポーネントにより、このようなプロシージャが可能になります。  
  
 このコンポーネントは、Windows フォームの環境用に設計されています。  サーバー環境に適したタイマーが必要な場合は、「[Introduction to Server\-Based Timers](http://msdn.microsoft.com/ja-jp/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)」を参照してください。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.Timer> コンポーネントを使用する場合に、いくつかの制限があります。  詳細については、「[Windows フォームの Timer コンポーネントの Interval プロパティの制限](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)」を参照してください。  
  
### Timer コンポーネントで設定された間隔でプロシージャを実行するには  
  
1.  <xref:System.Windows.Forms.Timer> をフォームに追加します。  プログラムでこれを実行する方法については、次の例のセクションを参照してください。  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] も、コンポーネントをフォームに追加する方法をサポートします。  「[方法 : ユーザー インターフェイスを持たないコントロールを Windows フォームに追加する](http://msdn.microsoft.com/library/becyw7bz\(v=vs.110\))」も参照してください。  
  
2.  タイマーの <xref:System.Windows.Forms.Timer.Interval%2A> プロパティ \(ミリ秒\) を設定します。  このプロパティは、プロシージャを再度実行する前に、経過する時間の長さを決定します。  
  
    > [!NOTE]
    >  タイマー イベントの発生頻度が高いと、イベントに対応するときに使用されるプロセッサ時間も長くなります。  これにより、全体的なパフォーマンスが低下します。  必要な間隔よりも小さな値を設定しないでください。  
  
3.  <xref:System.Windows.Forms.Timer.Tick> イベント ハンドラーで適切なコードを作成します。  このイベントで記述したコードは、<xref:System.Windows.Forms.Timer.Interval%2A> プロパティで指定した間隔で実行されます。  
  
4.  <xref:System.Windows.Forms.Timer.Enabled%2A> プロパティを `true` に設定して、タイマーを開始します。  <xref:System.Windows.Forms.Timer.Tick> イベントの発生が開始され、プロシージャが指定された間隔で実行されます。  
  
5.  適切なタイミングで <xref:System.Windows.Forms.Timer.Enabled%2A> プロパティを `false` に設定し、プロシージャがもう一度実行されることがないようにします。  間隔を `0` に設定すると、タイマーの停止が発生しません。  
  
## 使用例  
 この最初のコード例は、1 秒単位で 1 日の時間を追跡します。  フォーム上で <xref:System.Windows.Forms.Button>、<xref:System.Windows.Forms.Label>、および <xref:System.Windows.Forms.Timer> コンポーネントを使用します。  <xref:System.Windows.Forms.Timer.Interval%2A> プロパティが 1000 \(1 秒に等しい\) に設定されます。  <xref:System.Windows.Forms.Timer.Tick> イベントで、ラベルのキャプションが現在の時刻に設定されます。  ボタンをクリックしたときに、<xref:System.Windows.Forms.Timer.Enabled%2A> プロパティが `false` に設定されると、タイマーがラベルのキャプションを更新しなくなります。  次のコード例は、`Button1` という名前の <xref:System.Windows.Forms.Button> コントロール、`Timer1` という名前の <xref:System.Windows.Forms.Timer> コントロール、および `Label1` という名前の <xref:System.Windows.Forms.Label> コントロールがあるフォームを持っている必要があります。  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)     
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,    
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,   
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
  
```  
  
## 使用例  
 この 2 つ目のコード例は、ループが終了するまでにプロシージャを 600 ミリ秒ごとに実行します。  次のコード例は、`Button1` という名前の <xref:System.Windows.Forms.Button> コントロール、`Timer1` という名前の <xref:System.Windows.Forms.Timer> コントロール、および `Label1` という名前の <xref:System.Windows.Forms.Label> コントロールがあるフォームを持っている必要があります。  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)     
{  
   if (counter >= 10)   
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)   
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## 参照  
 <xref:System.Windows.Forms.Timer>   
 [Timer コンポーネント](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)   
 [Timer コンポーネントの概要](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)