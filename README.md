<div align="center">

## \.\.\.ooo0000 Modem Thing 0000ooo\.\.\.


</div>

### Description

It turns your modem on and off an amount of times that you define. Good for

annoying someone on the phone that is pissing you off!
 
### More Info
 
It might be possible that this could hurt your modem. I have done this 6000 times before and it didn't affect it any...


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Jake McCurry](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jake-mccurry.md)
**Level**          |Unknown
**User Rating**    |3.5 (28 globes from 8 users)
**Compatibility**  |VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Complete Applications](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/complete-applications__1-27.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jake-mccurry-ooo0000-modem-thing-0000ooo__1-2884/archive/master.zip)





### Source Code

```
'make a command button name Command1 make its caption "Begin"
'make a Textbox name Textbox1
'make a timer called Timer1 and make it unenabled interval = 500
'make a timer called Timer2 and make its interval 455
'Make a label called Label1
Private Sub Command1_Click()
Do Until Label1.Caption = Text1.Text
Timer1.Enabled = True
PhoneNumber$ = "123-4567" 'isn't important never dials
Open "COM2:" For Output As #1 'or COM1
Print #1, "ATDT" & PhoneNumber$ & Chr$(13)
Label1.Caption = Label1.Caption + 1
Close #1
Loop
End Sub
Private Sub Form_Resize()
On Error GoTo a
Form1.Height = 2715
Form1.Width = 3690
'another good way to do this is makes form1.borderstyle = 1
a:
End Sub
Private Sub Text1_KeyDown(KeyCode As Integer, Shift As Integer)
Select Case KeyCode
  Case vbKeyReturn:
    Do Until Label1.Caption = Text1.Text
    Timer1.Enabled = True
    PhoneNumber$ = "123-4567" 'this number isn't important it never dials!
    Open "COM2:" For Output As #1 'or COM1
    Print #1, "ATDT" & PhoneNumber$ & Chr$(13)
    Label1.Caption = Label1.Caption + 1
    Close #1
        Loop
  End Select
End Sub
Private Sub Timer1_Timer()
If Label1.Caption = Text1.Text Then
Label1.Caption = "0"
End If
End Sub
Private Sub Timer2_Timer()
  Dim a
a = Int(Rnd * 15) + 1
Text1.ForeColor = QBColor(a)
End Sub
```

