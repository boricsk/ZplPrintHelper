<p align="center">
  <img src=https://devnullsec.hu/logo_small.svg height="64" width="64">
</p>

## ZPL Code Printing management
### C# helper class for handling ZPL code print


- Usage
> You can send ZPL code to your local or network Zebra printers. Use print ZPL codes only! Example usage: 

```csharp
using ZplPrintHelper;
namespace ZplPrintDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            string zplCode = "^XA^FO50,50^ADN,36,20^FDHello Zebra!^FS^XZ";
            string printerName = "GK420d";
            string docName = "Zebra Print";
            //Send ZPL to your local printer. 3. parameter is optional, default value is "Zebra Print"
            //Return value true -> print success else false
            ZplPrint.SendZplToLocalPrinter(printerName, zplCode, docName);
            
            //Test connection. The second and third parameter is optional, defaults : 9100 (Default ports of Zebra printers) and 2000 (Timeout value 2 sec.)
            // return true if the connection success.
            ZplPrint.TestTcpConnection("127.0.0.5", 9100, 2000);

            //Send ZPL to your network printer. 3. parameter is optional, defaults : 9100 (Default ports of Zebra printers)
            // retun true is the print was success
            ZplPrint.SendZplToNetworkPrinter("127.0.0.5", zplCode, 9100);
        }
    }
}
```
<br>
<p align="center">
  <a href="https://www.nuget.org/packages/MifareClassic/1.0.0" target="_blank" >
    <img src="./nuget_logo.png" alt="NuGet Page">
  </a>
</p>
