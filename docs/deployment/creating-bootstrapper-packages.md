---
title: Önyükleyici paketleri oluşturma
ms.custom: ''
ms.date: 05/02/2018
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [Visual Studio], prerequisites
- deploying applications [Visual Studio], custom prerequisites
- prerequisites, custom
- RedistList file
- custom prerequisites
- redistributables list
ms.assetid: ba1a785b-693d-446b-bcae-b88cadee73d1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 29faeafb56c5c077602a3dbcba5ecbb6bb2ab118
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="create-bootstrapper-packages"></a>Önyükleyici paketleri oluşturma
Kurulum programı algılar ve Windows Installer (.msi) dosyaları ve yürütülebilir programları gibi yeniden dağıtılabilir bileşenleri yüklemek için yapılandırılmış bir genel yükleyicidir. Yükleyici bir önyükleyici de denir. Bir dizi bileşen yüklemesini yönetmek için meta veriler belirtin XML bildirimlerine ile programlanmış.  Her yeniden dağıtılabilir bileşeni ya da önkoşul, bir önyükleyici paketidir. Önyükleyici paketi, dizinler ve önkoşul nasıl yükleneceğini açıklayan bildirim dosyaları içeren dosyaları grubudur. 
  
Önyükleyici ilk Önkoşullar zaten yüklü olup olmadığını algılar. İlk Önkoşullar yüklü değilse, önyükleyici lisans sözleşmelerini gösterir. İkinci olarak, son kullanıcı lisans sözleşmelerini kabul ettikten sonra yükleme önkoşulları başlar. Aksi takdirde, tüm Önkoşullar algılanmazsa, önyükleyici yalnızca uygulama yükleyici başlatır.  
  
## <a name="create-custom-bootstrapper-packages"></a>Özel önyükleyici paketleri oluşturma  
Visual Studio'daki XML Düzenleyicisi'ni kullanarak önyükleyici bildirimler oluşturabilir. Önyükleyici paketi oluşturma örneği görmek için bkz: [izlenecek yol: bir gizlilik İstemi ile özel bir önyükleyici oluşturma](../deployment/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt.md).  
  
Önyükleyici paketi oluşturmak için ürün bildirimi oluşturmanız gerekir ve her biri için bir paket bildirimi de bir bileşen sürümü yerelleştirilmiş.
  
* Ürün bildirimi *product.xml*, paket için herhangi bir dilden meta veri içeriyor. Yeniden dağıtılabilir bileşeni tüm yerelleştirilmiş sürümleri için ortak meta veriler içerir.  Bu dosyayı oluşturmak için bkz: [nasıl yapılır: Ürün bildirimi oluşturma](../deployment/how-to-create-a-product-manifest.md).
  
* Paket bildirimi *package.xml*, dile özgü meta veriler; içeren genellikle yerelleştirilmiş hata iletileri içerir. Bu bileşen yerelleştirilmiş her sürümü için en az bir paket bildirimi bir bileşen içermelidir. Bu dosyayı oluşturmak için bkz: [nasıl yapılır: bir paket bildirimi oluşturma](../deployment/how-to-create-a-package-manifest.md).
  
Bu dosyalar oluşturulduktan sonra ürün bildirim dosyası için özel önyükleyici adlı bir klasöre yerleştirin. Paket bildirim dosyası yerel adlı bir klasöre gider. Örneğin, İngilizce yeniden dağıtım için paket bildirim dosyası ise, dosya tr adlı bir klasöre yerleştirin. Ja Japonca ve Almanca için de gibi her yerel ayar için bu işlemi yineleyin. Son özel önyükleyici paketi aşağıdaki klasör yapısını olabilir.  

    ```
    CustomBootstrapperPackage
      product.xml
      CustomBootstrapper.msi
      de
        eula.rtf
        package.xml
      en
        eula.rtf
        package.xml
      ja
        eula.rtf
        package.xml
    ```
  
Ardından, yeniden dağıtılabilir dosyaları önyükleyici klasör konumuna kopyalayın. Daha fazla bilgi için bkz: [nasıl yapılır: yerelleştirilmiş önyükleyici paketi oluşturma](../deployment/how-to-create-a-localized-bootstrapper-package.md).
 
    *\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages*
    
veya  
    
    *\Program Files (x86)\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages*
  
Önyükleyici klasör konumu da belirleyebilirsiniz **yolu** aşağıdaki kayıt defteri anahtarı değerini:  
  
    *HKLM\Software\Microsoft\GenericBootstrapper\11.0*
  
64 bitlik sistemlerde aşağıdaki kayıt defteri anahtarını kullanın:  
  
    *HKLM\Software\Wow6432Node\Microsoft\GenericBootstrapper\11.0*
  
Yeniden dağıtılabilir her bileşen, kendi alt paketler dizini altında görüntülenir. Gereken ürün bildirimi ve yeniden dağıtılabilir dosyaları, bu alt klasöre yerleştirin. Bileşen ve paket bildirimlerinin yerelleştirilmiş sürümleri göre kültür adı adlı klasörlerdeki konulmalıdır.  
  
Bu dosyalar önyükleyici klasöre kopyalandıktan sonra Visual Studio'da önyükleyici paketi otomatik olarak görünür. **Önkoşullar** iletişim kutusu. Özel önyükleyici paketi görünmüyorsa kapatıp **Önkoşullar** iletişim kutusu. Daha fazla bilgi için bkz: [Önkoşullar iletişim kutusu](../ide/reference/prerequisites-dialog-box.md).  
  
Aşağıdaki tabloda önyükleyici tarafından otomatik olarak doldurulur özellikleri gösterir.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|ApplicationName|Uygulamanın adı.|  
|ProcessorArchitecture|İşlemci ve BITS başına word bir yürütülebilir dosya tarafından hedeflenen Platform. Değerler aşağıdakileri içerir:<br /><br /> -Intel<br />-IA64<br />-AMD64|  
|[Version9x](https://msdn.microsoft.com/en-us/library/aa372490\(v=vs.140\).aspx)|Microsoft Windows 95, Windows 98 veya Windows ME işletim sistemleri için sürüm numarası. Sürümün sözdizimi Major.Minor.ServicePack öğesidir.|  
|[VersionNT](https://msdn.microsoft.com/en-us/library/aa372495\(v=vs.140\).xaspx)|Windows NT, Windows 2000, Windows XP, Windows Vista, Windows Server 2008 veya Windows 7 işletim sistemleri için sürüm numarası. Sürümün sözdizimi Major.Minor.ServicePack öğesidir.|  
|[VersionMSI](https://msdn.microsoft.com/en-us/library/aa372493\(v=vs.140\).aspx)|Windows Installer derlemesinin (msi.dll) sürümü yükleme sırasında çalıştırın.|  
|[AdminUser](https://msdn.microsoft.com/en-us/library/aa367545\(v=vs.140\).aspx)|Kullanıcının yönetici ayrıcalıkları varsa bu özelliği ayarlayın. True veya false değerleri.|  
|InstallMode|Yükleme modu burada yüklenmesine izin bileşen gerektiğini gösterir. Değerler aşağıdakileri içerir:<br /><br /> -HomeSite - Önkoşullar satıcının Web sitesinden yüklenir.<br />-SpecificSite - Önkoşullar seçtiğiniz konumdan yüklenir.<br />Uygulama aynı konumda - SameSite - Önkoşullar yüklendi.|  
  
## <a name="separating-redistributables-from-application-installations"></a>Yeniden dağıtılabilir öğeleri uygulama yüklemelerinden ayırma  
Yeniden dağıtılabilir dosyaların Kurulum projelerinde dağıtılmasını engelleyebilirsiniz. Bunu yapmak için .NET Framework dizininiz RedistList klasöründe yeniden dağıtılabilir listesi oluşturun:  
  
`%ProgramFiles%\Microsoft.NET\RedistList`  
  
Yeniden dağıtılabilir listesi aşağıdaki biçimi kullanarak ad vermemelisiniz bir XML dosyasıdır: *şirket adı*. *Bileşen adı*. RedistList.xml. Bu nedenle, örneğin, bileşen Acme tarafından yapılan Datawidgets çağrılırsa, kullanın *Acme.DataWidgets.RedistList.xml*. Yeniden dağıtılabilir listenin içeriği örneği şuna benzeyebilir:  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<FileList Redist="Acme.DataWidgets" >  
<File AssemblyName="Acme.DataGrid" Version="1.0.0.0" PublicKeyToken="b03f5f7f11d50a3a" Culture="neutral" ProcessorArchitecture="MSIL" InGAC="true" />  
</FileList>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: ClickOnce uygulamasıyla Önkoşulları Yükleme](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [Önkoşullar iletişim kutusu](../ide/reference/prerequisites-dialog-box.md)   
 [Ürün ve paket şema başvurusu](../deployment/product-and-package-schema-reference.md)   
 [Visual Studio 2005 önyükleyicisi başlatmak için kullanın](http://go.microsoft.com/fwlink/?LinkId=107537)