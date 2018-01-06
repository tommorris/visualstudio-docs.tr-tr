---
title: "Nasıl yapılır: Ürün bildirimi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- product files [ClickOnce]
- product files [Windows Installer]
- prerequisites, custom bootstrapper package
- dependencies, custom bootstrapper package
ms.assetid: 2d316aaa-8bc0-4ce5-90ab-23b3eac0b5dd
caps.latest.revision: "10"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 071bfa46df7e11f760bc32cda0a732388835d2d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-product-manifest"></a>Nasıl yapılır: Ürün Bildirimi Oluşturma
Uygulamanız için önkoşulları dağıtmak için bir önyükleyici paketi oluşturabilirsiniz. Paket bildirimi ancak tek bir ürün bildirim dosyası her yerel ayar için bir önyükleyici paketi içerir. Paket bildirimi paketinizin yerelleştirmeye özgü yönlerini içerir. Bu dizeler, son kullanıcı lisans sözleşmesi ve dil paketlerini içerir.  
  
 Ürün bildirimleri hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir paket bildirimi oluşturma](../deployment/how-to-create-a-package-manifest.md).  
  
## <a name="creating-the-product-manifest"></a>Ürün bildirimi oluşturma  
  
#### <a name="to-create-the-product-manifest"></a>Ürün bildirimi oluşturmak için  
  
1.  Önyükleyici paketi için bir dizin oluşturun. Bu örnek, C:\package kullanır.  
  
2.  Visual Studio'da adlı yeni bir XML dosyası oluşturma `product.xml`ve C:\package klasörüne kaydedin.  
  
3.  XML ad alanı ve ürün kodu için paket açıklamak için aşağıdaki XML ekleyin. Ürün kodunu paket için benzersiz bir tanımlayıcı ile değiştirin.  
  
    ```  
    <Product  
    xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"   
    ProductCode="Custom.Bootstrapper.Package">  
    ```  
  
4.  Paketi bir bağımlılık olduğunu belirtmek için XML ekleyin. Bu örnek, bir bağımlılık Microsoft Windows Installer 3.1 kullanır.  
  
    ```  
    <RelatedProducts>  
        <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />  
      </RelatedProducts>  
    ```  
  
5.  Önyükleyici paketinde bulunan tüm dosyaları listelemek için XML ekleyin. Bu örnek paket dosyası adı CorePackage.msi kullanır.  
  
    ```  
    <PackageFiles>  
        <PackageFile Name="CorePackage.msi"/>  
    </PackageFiles>  
    ```  
  
6.  Kopyalama veya CorePackage.msi dosyasını C:\package klasörüne taşıyın.  
  
7.  Önyükleyici komutlarını kullanarak paketi yüklemek için XML ekleyin. Önyükleyici otomatik olarak ekler **/qn** sessizce yükleyecek .msi dosyasına bayrağı. Dosyanın .exe olması durumunda önyükleyici Kabuğu'nu kullanarak .exe dosyasını çalıştırır. Aşağıdaki XML CorePackage.msi öğesine bağımsız değişkenler gösterir, ancak komut satırı bağımsız değişkeni bağımsız değişkenler özniteliği koyabilirsiniz.  
  
    ```  
    <Commands>  
        <Command PackageFile="CorePackage.msi" Arguments="">  
    ```  
  
8.  Bu önyükleyici paketinin yüklü olup olmadığını denetlemek için aşağıdaki XML ekleyin. Ürün kodunu yeniden dağıtılabilir bileşeni için GUID ile değiştirin.  
  
    ```  
    <InstallChecks>  
        <MsiProductCheck   
            Property="IsMsiInstalled"   
            Product="{XXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>  
    </InstallChecks>  
    ```  
  
9. Önyükleyici bileşeninin zaten yüklüyse, bağlı olarak önyükleyici davranışını değiştirmek için XML ekleyin. Bileşeni yüklüyse, önyükleyici paketi çalışmaz. Aşağıdaki XML bu bileşen yönetici ayrıcalıkları gereklidir çünkü geçerli kullanıcının yönetici olup olmadığını denetler.  
  
    ```  
    <InstallConditions>  
        <BypassIf   
           Property="IsMsiInstalled"   
           Compare="ValueGreaterThan" Value="0"/>  
        <FailIf Property="AdminUser"   
            Compare="ValueNotEqualTo" Value="True"  
            String="NotAnAdmin"/>  
    </InstallConditions>  
    ```  
  
10. Çıkış kodları yüklemenin başarılı olup olmadığını ve yeniden başlatma gerekli olup olmadığını ayarlamak için XML ekleyin. Aşağıdaki XML hata ve FailReboot çıkış önyükleyici paketleri yüklemeye devam edeceğini gösteren kodları gösterir.  
  
    ```  
    <ExitCodes>  
        <ExitCode Value="0" Result="Success"/>  
        <ExitCode Value="1641" Result="SuccessReboot"/>  
        <ExitCode Value="3010" Result="SuccessReboot"/>  
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>  
    </ExitCodes>  
    ```  
  
11. Önyükleyici komutlar bölümünü sonlandırmak için aşağıdaki XML ekleyin.  
  
    ```  
        </Command>  
    </Commands>  
    ```  
  
12. C:\package klasörünü Visual Studio önyükleyici dizinine taşıyın. Visual Studio 2010 için bu \Program SDKs\Windows\v7.0A\Bootstrapper\Packages dizinidir.  
  
## <a name="example"></a>Örnek  
 Ürün bildirimi özel Önkoşullar için yükleme yönergeleri içerir.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<Product  
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
  ProductCode="Custom.Bootstrapper.Package">  
  
  <RelatedProducts>  
    <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />  
  </RelatedProducts>  
  
  <PackageFiles>  
    <PackageFile Name="CorePackage.msi"/>  
  </PackageFiles>  
  
  <InstallChecks>  
    <MsiProductCheck Product="IsMsiInstalled"   
      Property="{XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>  
  </InstallChecks>  
  
  <Commands>  
    <Command PackageFile="CorePackage.msi" Arguments="">  
  
      <InstallConditions>  
        <BypassIf Property="IsMsiInstalled"  
          Compare="ValueGreaterThan" Value="0"/>  
        <FailIf Property="AdminUser"   
          Compare="ValueNotEqualTo" Value="True"  
         String="NotAnAdmin"/>  
      </InstallConditions>  
  
      <ExitCodes>  
        <ExitCode Value="0" Result="Success"/>  
        <ExitCode Value="1641" Result="SuccessReboot"/>  
        <ExitCode Value="3010" Result="SuccessReboot"/>  
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>  
      </ExitCodes>  
    </Command>  
  </Commands>  
</Product>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ürün ve Paket Şema Başvurusu](../deployment/product-and-package-schema-reference.md)