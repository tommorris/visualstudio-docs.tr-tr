---
title: 'İzlenecek yol: JavaScript kullanarak bir SDK oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: a8c89d5d-5b78-4435-817f-c5f25ca6d715
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2132269329c8b6af3ac846596adea7b3462db5bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144222"
---
# <a name="walkthrough-creating-an-sdk-using-javascript"></a>İzlenecek yol: JavaScript kullanarak bir SDK oluşturma
Bu kılavuz, JavaScript SDK'sı bir Visual Studio Uzantısı (VSIX) olarak basit bir matematik oluşturmak için kullanılacak öğretir.  İzlenecek yol aşağıdaki bölümlere ayrılır:  
  
-   [SimpleMathVSIX uzantı SDK projesi oluşturmak için](../extensibility/walkthrough-creating-an-sdk-using-javascript.md#createSimpleMathVSIX)  
  
-   [SDK'yı kullanan örnek bir uygulama oluşturmak için](../extensibility/walkthrough-creating-an-sdk-using-javascript.md#createSampleApp)  
  
 JavaScript için sınıf kitaplığı proje türü yok. Bu kılavuzda, örnek arithmetic.js dosyasını doğrudan VSIX projesinde oluşturulur. Yöntem, ilk derleme ve bir Windows mağazası uygulaması JavaScript ve CSS dosyaları test önerilir — kullanarak örneğin, **boş uygulama** şablonu — bir VSIX proje ile yerleştirmeden önce.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
##  <a name="createSimpleMathVSIX"></a> SimpleMathVSIX uzantı SDK projesi oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  Şablon kategorileri listesinde altında **Visual C#** seçin **genişletilebilirlik**ve ardından **VSIX proje** şablonu.  
  
3.  İçinde **adı** metin kutusunda, belirtin `SimpleMathVSIX` ve **Tamam** düğmesi.  
  
4.  Varsa **Visual Studio Paketi Sihirbazı** görünen seçin **sonraki** düğmesini **Hoş Geldiniz** sayfasında ve ardından **7'in sayfa 1**, seçin **Son** düğmesi.  
  
     Ancak **bildirim Tasarımcısı** açar, biz tutmak bu kılavuzda basit bildirim dosyasını doğrudan değiştirerek.  
  
5.  İçinde **Çözüm Gezgini**source.extension.vsixmanifest dosya için kısayol menüsünü açın ve ardından **görünümü kodu**. Varolan dosyanın içeriğini değiştirmek için bu kodu kullanın.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011" xmlns:d="http://schemas.microsoft.com/developer/vsx-schema-design/2011">  
      <Metadata>  
        <Identity Id="SimpleMathVSIX" Version="1.0" Language="en-US" Publisher="myname" />  
        <DisplayName>Simple Math</DisplayName>  
        <Description>Does basic arithmetic calculations.</Description>  
      </Metadata>  
      <Installation Scope="Global" AllUsers="true">  
        <InstallationTarget Id="Microsoft.ExtensionSDK" TargetPlatformIdentifier="Windows" TargetPlatformVersion="v8.0" SdkName="SimpleMath" SdkVersion="1.0" />  
      </Installation>  
      <Dependencies>  
        <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" d:Source="Manual" Version="4.5" />  
      </Dependencies>  
      <Assets>  
        <Asset Type="Microsoft.ExtensionSDK" d:Source="File" Path="SDKManifest.xml" />  
      </Assets>  
    </PackageManifest>  
    ```  
  
6.  İçinde **Çözüm Gezgini**SimpleMathVSIX proje için kısayol menüsünü açın ve ardından **Ekle**, **yeni öğe**.  
  
7.  İçinde **veri** kategorisi, select **XML dosyası**, dosya adı `SDKManifest.xml`ve seçin **Ekle** düğmesi.  
  
8.  İçinde **Çözüm Gezgini**SDKManifest.xml dosya için kısayol menüsünü açın ve ardından **açmak** dosyasında görüntülemek için **XML Düzenleyicisi**.  
  
9. SDKManifest.xml dosyasına aşağıdaki kodu ekleyin.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <FileList  
      DisplayName="Simple Math"  
      MinVSVersion="14.0"  
      AppliesTo="JavaScript+WindowsAppContainer"  
      SupportsMultipleVersions="Error"  
      MoreInfo="http://www.msdn.microsoft.com/">  
  
      <!-- JS -->  
      <File Content="js\arithmetic.js" />  
    </FileList>  
  
    ```  
  
10. İçinde **Çözüm Gezgini**, SDKManifest.xml dosyası için kısayol menüsünden seçin **özellikleri**.  
  
11. İçinde **özellikleri** penceresindeki ayarlayın **Include in VSIX** özelliğine **doğru**.  
  
12. İçinde **Çözüm Gezgini**, SimpleMathVSIX proje kısayol menüsünden seçin **Ekle**, **yeni klasör**ve ardından klasörün adını `Redist`.  
  
13. Bu klasör yapısı oluşturmak amacıyla Redist klasörleriyle ekleyin:  
  
     \Redist\CommonConfiguration\Neutral\SimpleMath\js\  
  
14. \Js\ klasörü için kısayol menüsünden seçin **Ekle**, **yeni öğe**.  
  
15. Altında **Visual C# öğeleri**seçin **Web** kategori ve ardından **JavaScript dosyası** öğesi. Dosya adı `arithmetic.js`ve ardından **Ekle** düğmesi.  
  
16. Aşağıdaki kodu arithmetic.js ekleyin:  
  
    ```  
    (function (global) {  
        "use strict";  
        global.Arithmetic = {  
            add: function (firstNumber, secondNumber) {  
                return firstNumber + secondNumber;  
            },  
  
            subtract: function (firstNumber, secondNumber) {  
                return firstNumber - secondNumber;  
            },  
  
            multiply: function (firstNumber, secondNumber) {  
                return firstNumber * secondNumber;  
            },  
  
            divide: function (firstNumber, secondNumber) {  
                return firstNumber / secondNumber;  
            }  
        };  
    })(this);  
  
    ```  
  
17. İçinde **Çözüm Gezgini**, arithmetic.js dosyası için kısayol menüsünden seçin **özellikleri**. Bu özellik değişiklikleri yapın:  
  
    -   Ayarlama **Include in VSIX** özelliğine **doğru**.  
  
    -   Ayarlama **çıktı dizinine Kopyala** özelliğine **her zaman Kopyala**.  
  
18. İçinde **Çözüm Gezgini**, SimpleMathVSIX proje kısayol menüsünden seçin **yapı**.  
  
19. Derleme projesi için kısayol menüsünde başarıyla tamamlandıktan sonra seçin **dosya Gezgini'nde klasör Aç**. İçin \bin\Debug gidin\\, çalıştırıp `SimpleMathVSIX.vsix` yükleyin.  
  
20. Seçin **yükleme** düğmesi ve let yükleme tamamlandı.  
  
21. Visual Studio'yu yeniden başlatın.  
  
##  <a name="createSampleApp"></a> SDK'yı kullanan örnek bir uygulama oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  Şablon kategorileri listesinde altında **JavaScript**seçin **Windows mağazası**ve ardından **boş uygulama** şablonu.  
  
3.  İçinde **adı** kutusunda, belirtin `ArithmeticUI`. Seçin **Tamam** düğmesi.  
  
4.  İçinde **Çözüm Gezgini**ArithmeticUI proje için kısayol menüsünü açın ve ardından **Ekle**, **başvuru**.  
  
5.  Altında **Windows**, seçin **uzantıları**ve dikkat **basit matematik** görüntülenir.  
  
6.  Seçin **basit matematik** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.  
  
7.  İçinde **Çözüm Gezgini**altında **başvuruları**, dikkat **basit matematik** başvuru görüntülenir. Genişletin ve arithmetic.js içeren bir \js\ klasör olduğuna dikkat edin. Kaynak kodunuz yüklendiğini doğrulamak için arithmetic.js açabilirsiniz.  
  
8.  Default.htm içeriğini değiştirmek için aşağıdaki kodu kullanın.  
  
    ```  
    <!DOCTYPE html>  
    <html>  
    <head>  
        <meta charset="utf-8" />  
        <title>ArithmeticUI</title>  
  
        <!-- WinJS references -->  
        <link href="//Microsoft.WinJS.1.0/css/ui-dark.css" rel="stylesheet" />  
        <script src="//Microsoft.WinJS.1.0/js/base.js"></script>  
        <script src="//Microsoft.WinJS.1.0/js/ui.js"></script>  
  
        <!-- ArithmeticUI references -->  
        <link href="/css/default.css" rel="stylesheet" />  
        <script src="/js/default.js"></script>  
        <script src="/SimpleMath/js/arithmetic.js"></script>  
    </head>  
    <body>  
        <form>  
        <div id="calculator" class="ms-grid">  
            <input name="firstNumber" id="firstNumber" type="number" step="any">  
            <div id="operators">  
                <button class="operator" type="button">+</button>  
                <button class="operator" type="button">-</button>  
                <button class="operator" type="button">*</button>  
                <button class="operator" type="button">/</button>  
            </div>  
            <input id="secondNumber" type="number">  
            <button class="calculate" type="button">=</button>  
            <input id="result" type="number" name="result" disabled="" readonly="">  
        </div>  
        </form>  
    </body>  
    </html>  
    ```  
  
9. Sonraki kod \js\default.js içeriğini değiştirmek için kullanın.  
  
    ```  
    (function () {  
        "use strict";  
  
        var app = WinJS.Application;  
        var operation = null;  
  
        function calculateResult() {  
            var firstNumber = parseFloat(document.querySelector("#firstNumber").value),  
                secondNumber = parseFloat(document.querySelector("#secondNumber").value),  
                result = 0;  
  
            if (isNaN(firstNumber) || isNaN(secondNumber)) {  
                result = 0;  
            }  
            else {  
                switch (operation) {  
                    case "+":  
                        result = Arithmetic.add(firstNumber, secondNumber);  
                        break;  
                    case "-":  
                        result = Arithmetic.subtract(firstNumber, secondNumber);  
                        break;  
                    case "*":  
                        result = Arithmetic.multiply(firstNumber, secondNumber);  
                        break;  
                    case "/":  
                        result = Arithmetic.divide(firstNumber, secondNumber);  
                        break;  
                    default:  
                }  
            }  
            document.querySelector("#result").value = result.toString();  
        }  
  
        app.onactivated = function (args) {  
            document.querySelector("#calculator").addEventListener("click", function (event) {  
                if (event.target.tagName.toLowerCase() === "button") {  
                    switch (event.target.className) {  
                        case "operator":  
                            operation = event.target.innerText;  
                            break;  
                        case "calculate":  
                            calculateResult();  
                            break;  
                        default:  
                            break;  
                    }  
                }  
            });  
        };  
  
        app.start();  
    })();  
    ```  
  
10. \Css\default.css içeriğini bu kod ile değiştirin:  
  
    ```  
    form {  
        display: -ms-grid;  
        -ms-grid-rows: 1fr auto 1fr;  
        -ms-grid-columns: 1fr auto 1fr;  
        height: 100%;  
        width: 100%;  
    }  
  
    button, input[type=number] {  
        margin-right: 5px;  
        -ms-grid-row-align: center;  
    }  
  
    #calculator {  
        -ms-grid-column: 2;  
        -ms-grid-row: 2;  
        display: -ms-grid;  
        -ms-grid-rows: 1fr;  
        -ms-grid-columns: auto min-content auto auto auto;  
    }  
  
    .ms-grid input {  
        width: 5em;  
    }  
  
    #firstNumber {  
        -ms-grid-column: 1;  
        -ms-grid-row-align: center;  
    }  
  
    #operators {  
        -ms-grid-column: 2;  
        -ms-grid-row-align: center;  
    }  
  
        #operators button.operator {  
            margin-bottom: 5px;  
            height: 40px;  
        }  
  
    #secondNumber {  
        -ms-grid-column: 3;  
    }  
  
    button.calculate {  
        -ms-grid-column: 4;  
        -ms-grid-row-align: center;  
        height: 40px;  
    }  
  
    #result {  
        -ms-grid-column: 5;  
    }  
  
    ```  
  
11. Derleme ve uygulamayı çalıştırmak için F5 tuşuna seçin.  
  
12. Uygulama kullanıcı Arabirimi, herhangi iki sayıyı girin, bir işlem seçin ve ardından **=** düğmesi. Doğru sonucu görünür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazılık Geliştirme Seti Oluşturma](../extensibility/creating-a-software-development-kit.md)