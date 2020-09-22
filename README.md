<div align="center">

## ASP\.NET Popup Windows


</div>

### Description

Show any Page as a modal popup window in ASP.NET.
 
### More Info
 
'Usage :

' searchButton.Attributes.Add("onclick", BuildPopUpScript("PopupPage.aspx", 800, 600))


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Claudio Cesp&\#243;n](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/claudio-cesp-243-n.md)
**Level**          |Intermediate
**User Rating**    |4.7 (14 globes from 3 users)
**Compatibility**  |ASP\.NET
**Category**       |[Math](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/math__10-12.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/claudio-cesp-243-n-asp-net-popup-windows__10-4475/archive/master.zip)





### Source Code

```
Public Function BuildPopUpScript(ByVal Page As String, _
                    Optional ByVal dialogWidth As Int32 = 255, _
                    Optional ByVal dialogHeight As Int32 = 255, _
                    Optional ByVal modal As Boolean = True) As String
    Try
      Dim jsmodal As String
      If modal Then
        jsmodal &= "if (window.showModalDialog)"
        jsmodal &= "{window.showModalDialog('" & Page.Trim & "','name',"
        jsmodal &= "'dialogWidth:" & dialogWidth & "px;dialogHeight:" & dialogHeight & "px;status:no;help:no;scroll:no');}"
        jsmodal &= "else{"
        jsmodal &= "window.open('" & Page.Trim & "','name','height=" & dialogHeight & ","
        jsmodal &= "width=" & dialogWidth & ",toolbar=no,directories=no,status=no,"
        jsmodal &= "menubar=no,scrollbars=no,resizable=no,modal=yes');"
        jsmodal &= "}"
      Else
        jsmodal &= "window.open('" & Page.Trim & "','name','height=" & dialogHeight & ","
        jsmodal &= "width=" & dialogWidth & ",toolbar=no,directories=no,status=no,"
        jsmodal &= "menubar=no,scrollbars=no,resizable=no,modal=no');"
      End If
      Return jsmodal
    Catch ex As Exception
      Return "alert(" & ex.Message & ");"
    End Try
  End Function
```

