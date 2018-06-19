---
title: ActiveXObject nesnesi (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- ActiveXObject
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ActiveXObject object
- Automation objects, ActiveXObject objects
ms.assetid: 9c7bed07-853f-48aa-92db-3131324746ec
caps.latest.revision: 34
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77bb743aeab563f7d7711e4caa9a0fcf0b45ff58
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789257"
---
# <a name="activexobject-object-javascript"></a>ActiveXObject Nesnesi (JavaScript)
Otomasyon nesnesini etkinleştirir ve ona bir başvuru döndürür.  
  
 Bu nesne yalnızca Automation nesnelerini örneklemek için kullanılır ve üyeleri yoktur.  
  
> [!WARNING]
>  Bu nesne bir Microsoft uzantısıdır ve Internet Explorer'da yalnızca içinde değil desteklenen [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
newObj = new ActiveXObject(servername.typename[, location])  
```  
  
## <a name="parameters"></a>Parametreler  
 `newObj`  
 Gerekli. Değişken adına `ActiveXObject` atanır.  
  
 `servername`  
 Gerekli. Nesneyi sağlayan uygulamanın adı.  
  
 `typename`  
 Gerekli. Oluşturulacak nesnenin türü ya da sınıfı.  
  
 `location`  
 İsteğe bağlı. Nesnenin oluşturulacağı ağ sunucusunun adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Otomasyon sunucuları en az bir tür nesne sağlar. Örneğin, bir kelime işleme uygulaması bir uygulama nesnesi, bir belge nesnesi ve bir araç çubuğu nesnesi sağlayabilir.  
  
 Belirlemek mümkün olabilir `servername.typename` ana bilgisayar değerlerine `HKEY_CLASSES_ROOT` kayıt defteri anahtarı. Örneğin, burada, hangi programların yüklü olduğuna bağlı olarak burada bulabileceğiniz değerlere birkaç örnek verilmiştir:  
  
-   Excel.Application  
  
-   Excel.Chart  
  
-   Scripting.FileSystemObject  
  
-   WScript.Shell  
  
-   Word.Document  
  
> [!IMPORTANT]
>  ActiveX nesneleri güvenlik sorunları sunabilir. Kullanılacak `ActiveXObject`, ilgili güvenlik bölgesi için güvenlik ayarlarını Internet Explorer'da ayarlamanız gerekebilir. Örneğin, Yerel intranet bölgesi için genellikle bir özel ayarı "Komut dosyası oluşturma için güvenli olarak işaretlenmemiş ActiveX denetimlerini başlatın ve komut dosyasını oluşturun" olarak değiştirmeniz gerekir.  
  
 Kodunuzda kullanabileceğiniz bir Otomasyon nesnesi üyelerini tanımlamak için bir COM Nesne Tarayıcısı gibi kullanmanız gerekebilir [OLE/COM Nesne Görüntüleyicisi](http://msdn.microsoft.com/library/d0kh9f4c.aspx), başvuru belgeleri Otomasyon nesne için kullanılabilir.  
  
 Bir Otomasyon nesnesi oluşturmak için yeni Ata `ActiveXObject` bir nesne değişkeni için:  
  
```JavaScript  
var ExcelApp = new ActiveXObject("Excel.Application");  
var ExcelSheet = new ActiveXObject("Excel.Sheet");  
```  
  
 Bu kod nesneyi oluşturan uygulamayı başlatır (bu durumda, bir Microsoft Excel çalışma sayfası). Bir nesne oluşturulduğunda, ona tanımladığınız nesne değişkenini kullanarak kod içinde başvurabilirsiniz. Aşağıdaki örnekte, özellikleri ve yöntemleri nesne değişkeni kullanarak yeni nesnenin erişim `ExcelSheet` ve uygulama nesnesi ve ActiveSheet.Cells koleksiyonu dahil olmak üzere diğer Excel nesneleri.  
  
```JavaScript  
// Make Excel visible through the Application object.  
ExcelSheet.Application.Visible = true;  
// Place some text in the first cell of the sheet.  
ExcelSheet.ActiveSheet.Cells(1,1).Value = "This is column A, row 1";  
// Save the sheet.  
ExcelSheet.SaveAs("C:\\TEST.XLS");  
// Close Excel with the Quit method on the Application object.  
ExcelSheet.Application.Quit();  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Şu belge modlarında desteklenir: Quirks, Internet Explorer 6 standartları, Internet Explorer 7 standartları, Internet Explorer 8 standartları, Internet Explorer 9 standartları, Internet Explorer 10 standartları ve Internet Explorer 11 standartları. İçinde desteklenmez [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Bkz. [Sürüm Bilgisi](../../javascript/reference/javascript-version-information.md).  
  
> [!NOTE]
>  Oluşturma bir `ActiveXObject` uzak bir sunucuda desteklenmeyen [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)] veya sonraki bir sürümü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [GetObject işlevi](../../javascript/reference/getobject-function-javascript.md)   
 [Benzersiz kimlik doğrulaması Sihirli, HTML5/WCF örnek uygulaması kullanma](http://code.msdn.microsoft.com/Unique-Authentication-f32d2da0)