---
title: Önyükleyici paketleri oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 794d569504e46627c9387046b381fdb843a7818e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="creating-bootstrapper-packages"></a>Önyükleyici Paketleri Oluşturma
Kurulum programı algılar ve Windows Installer (.msi) dosyaları ve yürütülebilir programları gibi yeniden dağıtılabilir bileşenleri yüklemek için yapılandırılmış bir genel yükleyicidir. Yükleyici bir önyükleyici de denir. Bir dizi bileşen yüklemesini yönetmek için meta veriler belirtin XML bildirimlerine ile programlanmış.  
  
 Önyükleyici ilk Önkoşullar zaten yüklü olup olmadığını algılar. İlk Önkoşullar yüklü değilse, önyükleyici lisans sözleşmelerini gösterir. İkinci olarak, son kullanıcı lisans sözleşmelerini kabul ettikten sonra yükleme önkoşulları başlar. Aksi takdirde, tüm Önkoşullar algılanmazsa, önyükleyici yalnızca uygulama yükleyici başlatır.  
  
## <a name="creating-custom-packages"></a>Özel paketleri oluşturma  
 Visual Studio'daki XML Düzenleyicisi'ni kullanarak bildirimler oluşturabilir. Daha fazla bilgi için bkz: [nasıl yapılır: bir paket bildirimi oluşturma](../deployment/how-to-create-a-package-manifest.md) ve [nasıl yapılır: Ürün bildirimi oluşturma](../deployment/how-to-create-a-product-manifest.md). Önyükleyici paketi oluşturma örneği görmek için bkz: [izlenecek yol: bir gizlilik istemi göstermek için bir özel önyükleyici oluşturma](../deployment/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt.md).  
  
 Önyükleyici paketi oluşturma için yeniden dağıtılabilir bir EXE ya da MSI öğeyi Önyükleyici Bildirim Oluşturucusu biçiminde sağlamanız gerekir. Ardından, önyükleyici bildirim oluşturucusu aşağıdaki dosyaları oluşturur:  
  
-   Ürün bildirimi paketi için herhangi bir dilden meta veri içeren product.xml olabilir. Yeniden dağıtılabilir bileşeni tüm yerelleştirilmiş sürümleri için ortak meta veriler içerir.  
  
-   Paket bildirimi, dile özgü meta veriler içeren package.xml; Genellikle, yerelleştirilmiş hata iletilerini içerir. Bu bileşen yerelleştirilmiş her sürümü için en az bir paket bildirimi bir bileşen içermelidir.  
  
 Bu dosyalar oluşturulduktan sonra ürün bildirim dosyası için özel önyükleyici adlı bir klasöre yerleştirin. Paket bildirim dosyası yerel adlı bir klasöre gider. Örneğin, İngilizce yeniden dağıtım için paket bildirim dosyası ise, dosya tr adlı bir klasöre yerleştirin. Ja Japonca ve Almanca için de gibi her yerel ayar için bu işlemi yineleyin. Son özel önyükleyici paketi aşağıdaki klasör yapısını olabilir.  
  
 `CustomBootstrapperPackage`  
  
 `product.xml`  
  
 `CustomBootstrapper.msi`  
  
 `de`  
  
 `eula.rtf`  
  
 `package.xml`  
  
 `en`  
  
 `eula.rtf`  
  
 `package.xml`  
  
 `ja`  
  
 `eula.rtf`  
  
 `package.xml`  
  
 Son olarak, yeniden dağıtılabilir dosyaları önyükleyici klasör konumuna kopyalayın. Daha fazla bilgi için bkz: [nasıl yapılır: yerelleştirilmiş önyükleyici paketi oluşturma](../deployment/how-to-create-a-localized-bootstrapper-package.md).  
  
```  
\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages  
```  
  
 veya  
  
```  
\Program Files (x86)\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages  
```  
  
 Önyükleyici klasör konumu da belirleyebilirsiniz **yolu** aşağıdaki kayıt defteri anahtarı değerini:  
  
```  
HKLM\Software\Microsoft\GenericBootstrapper\11.0  
```  
  
 64 bit sistemlerde, aşağıdaki kayıt defteri anahtarını kullanın:  
  
```  
HKLM\Software\Wow6432Node\Microsoft\GenericBootstrapper\11.0  
```  
  
 Yeniden dağıtılabilir her bileşen, kendi alt paketler dizini altında görüntülenir. Ürün bildirimi ve yeniden dağıtılabilir dosyaları, bu alt klasör içine konur. Bileşen ve paket bildirimlerinin yerelleştirilmiş sürümleri göre kültür adı adlı alt klasörler yerleştirilir.  
  
 Bu dosyalar önyükleyici klasöre kopyalandıktan sonra önyükleyici paketi otomatik olarak Visual Studio önkoşullar iletişim kutusu görüntülenir. Özel önyükleyici paketi görünmüyorsa kapatıp Önkoşullar iletişim kutusu. Daha fazla bilgi için bkz: [Önkoşullar iletişim kutusu](../ide/reference/prerequisites-dialog-box.md).  
  
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
  
 Yeniden dağıtılabilir listesi aşağıdaki biçimi kullanarak ad vermemelisiniz bir XML dosyasıdır: *şirket adı*. *Bileşen adı*. RedistList.xml. Bileşen Acme tarafından yapılan Datawidgets çağrılırsa, örneğin, Acme.DataWidgets.RedistList.xml kullanın. Yeniden dağıtılabilir listenin içeriği örneği şuna benzeyebilir:  
  
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