---
title: Web sayfası (JavaScript) metin görüntüleme | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JavaScript, write
- JavaScript, writing text
ms.assetid: 3c2455e7-2402-45f2-9545-77a2b2490527
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a8c9ea9d0e0300a0d9b71b0b33d7c99c9ac3935c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789032"
---
# <a name="displaying-text-in-a-webpage-javascript"></a>Web Sayfasında Metin Görüntüleme (JavaScript)
Bir Web sayfasında metin görüntülemek için çeşitli yöntemler vardır. Her avantajları ve dezavantajları vardır ve belirli kullanıyor destekler.  
  
## <a name="displaying-text"></a>Metin Görüntüleme  
  
-   Metni görüntülemek için önerilen bir öğe oluşturun ve kendi textContent özelliğine yazmak için bir yoludur.  
  
    ```JavaScript  
    <div id="textDiv"></div>  
    <script type="text/javascript">  
        var div = document.getElementById("textDiv");  
        div.textContent = "my text";  
        var text = div.textContent;  
    </script>  
    ```  
  
     Bu örnekte, değeri `text` "benim" metindir. Ancak, alma ve ayarlama değer `textContent` üst düğümü üzerindeki özelliğini düğümün alt metin içeriği içerebilir. Aşağıdaki örnekte gösterilir `textContent` olan bir alt düğüm kümesinde değerinde dahil `textContent` üst düğümün:  
  
    ```JavaScript  
    <div id="textDiv">  
        <div id="nested"></div>  
    </div>  
    <script type="text/javascript">  
        var div = document.getElementById("textDiv");  
        var nestedDiv = document.getElementById("nested");  
        nestedDiv.textContent = "nested";  
  
        var text = "[" + div.textContent + "]";  
    </script>  
    ```  
  
     Bu örnekte, değeri `text` "[iç içe yerleştirilmiş]".  
  
-   Ayrıca bir öğe oluşturun ve yazma kendi [InnerHtml](http://msdn.microsoft.com/library/ie/ms533897\(v=vs.85\).aspx) veya [InnerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) özellikleri. Bu özellikleri ayarlama, yalnızca öğe kendisinde değil, alt öğelerini metinde etkiler. Ancak, bu özellikleri, ayrıca bazı dezavantajları vardır:  
  
    -   [InnerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) özelliği, tüm tarayıcılarda çalışmıyor, uyumluluk nedenleriyle önlemek isteyebilirsiniz.  
  
    -   [InnerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) özelliği CSS stilleri tarafından etkilenir ve öğenin gizli görünmez.  
  
    -   [InnerHtml](http://msdn.microsoft.com/library/ie/ms533897\(v=vs.85\).aspx) özelliğini alır ve iç içe geçmiş düğümleri ve metin ayarlar. Güvenli değil, komut dosyası ekleme saldırıları için kullanılabilir. Ayrıca, HTML etiketleri olmadan metne ayarlama daha önce tüm küme düğümleri kaldırır.  
  
-   Kullanabileceğiniz `document.write` bir öğe oluşturmak zorunda kalmadan yöntemi. Ancak, bu yöntemi kullanarak tüm web temizlenecek, istediğiniz olmayabilir sayfasını neden olur.  
  
     Aşağıdaki örnek, aşağıdakilerden birini kullanarak dezavantajları gösterir `document.write`. Komut dosyası her 5 saniyede zaman görüntülemek için tasarlanmıştır ancak zaman yalnızca iki kez gösterir. Zamana göre `document.write` ikinci kez adlı sayfa yükleniyor, tamamladıktan ve `document.write` sayfanın tamamını temizler (çağırır `document.open`). Bu noktada, `ShowTime` işlevi artık yok.  
  
    ```html  
    <!DOCTYPE html>  
    <html>  
    <head>  
    <script type="text/javascript">  
        function ShowTime()  
        {  
            var dt = new Date();  
            document.write(dt.toTimeString());  
            // var elem = document.getElementById("divElem");  
            // elem.textContent = dt.toTimeString();  
            window.setTimeout("ShowTime();", 5000);  
        }  
    </script>  
    </head>  
  
    <body>  
    <script type="text/javascript">  
        ShowTime();  
    </script>  
    <div id="myDiv"></div>  
    </body>  
    </html>  
  
    ```  
  
     Önceki kod düzeltmek için içeren kod satırı Kaldır `document.write` ve iki açıklamalı izleyen kod satırı açıklamadan çıkarın.  
  
-   Aynı zamanda bir `alert``prompt`, veya `confirm` açılır pencerede bir ileti görüntüler işlevi. Çoğu durumda, bir web tarayıcısında açılır pencere kullanmak iyi bir fikir değil. Çoğu modern tarayıcılar iletinizi değil görülebilir böylece otomatik olarak açılır pencereleri engelleme ayarlarına sahip. Ayrıca, kullanıcının Normal yollardan web sayfasını kapatmak mümkün kılan açılır pencereleri kullandığınızda sonsuz bir döngüde girmek mümkündür.