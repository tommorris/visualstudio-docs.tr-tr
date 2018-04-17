---
title: 'Nasıl yapılır: Paket bildirimi oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- package files [Windows Installer]
- package files [ClickOnce]
- prerequisites, custom bootstrapper package
- dependencies, custom bootstrapper packages
ms.assetid: 5aecc507-2764-42f2-ae6f-c227971cf0af
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: d36d6c1d4589fa24e4c3e7c53e041d07f359092b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-package-manifest"></a>Nasıl yapılır: Paket Bildirimi Oluşturma
Uygulamanız için önkoşulları dağıtmak için bir önyükleyici paketi kullanabilirsiniz. Paket bildirimi ancak tek bir ürün bildirim dosyası her yerel ayar için bir önyükleyici paketi içerir. Farklı yerelleştirilmiş sürümleri arasında paylaşılan işlev ürün bildirimine gitmelidir.  
  
 Paket bildirimleri hakkında daha fazla bilgi için bkz: [nasıl yapılır: Ürün bildirimi oluşturma](../deployment/how-to-create-a-product-manifest.md).  
  
## <a name="creating-the-package-manifest"></a>Paket bildirimi oluşturma  
  
#### <a name="to-create-the-package-manifest"></a>Paket bildirimi oluşturmak için  
  
1.  Önyükleyici paketi için bir dizin oluşturun. Bu örnek, C:\package kullanır.  
  
2.  İngilizce için en gibi yerel ada sahip bir dizin oluşturun.  
  
3.  Visual Studio'da adlı bir XML dosyası oluşturma `package.xml`ve C:\package\en klasörüne kaydedin.  
  
4.  Önyükleyici paketinin adını, bu yerelleştirilmiş paket bildirimi ve isteğe bağlı Lisans Sözleşmesi'ni culture listelemek için XML ekleyin. Aşağıdaki XML değişkenlerini kullanır `DisplayName` ve `Culture`, daha sonraki bir öğede tanımlanır.  
  
    ```  
    <Package  
        xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
        Name="DisplayName"  
        Culture="Culture"  
        LicenseAgreement="eula.txt">  
    ```  
  
5.  Yerel ayarlara özgü dizinde bulunan tüm dosyaları listelemek için XML ekleyin. Aşağıdaki XML için uygulanabilir eula.txt adlı bir dosya kullanır **tr** yerel ayar.  
  
    ```  
    <PackageFiles>  
      <PackageFile Name="eula.txt"/>  
    </PackageFiles>  
    ```  
  
6.  Önyükleyici paketi yönelik yerelleştirilebilir dizeler tanımlamak için XML ekleyin. Aşağıdaki XML tr yerel ayarı için hata dizeleri ekler.  
  
    ```  
      <Strings>  
        <String Name="DisplayName">Custom Bootstrapper Package</String>  
        <String Name="CultureName">en</String>  
        <String Name="NotAnAdmin">You must be an administrator to install   
    this package.</String>  
        <String Name="GeneralFailure">A general error has occurred while   
    installing this package.</String>  
    </Strings>  
    ```  
  
7.  C:\package klasörünü Visual Studio önyükleyici dizinine kopyalayın. Visual Studio 2010 için bu \Program SDKs\Windows\v7.0A\Bootstrapper\Packages dizinidir.  
  
## <a name="example"></a>Örnek  
 Paket bildirimi hata iletileri, yazılım lisans koşulları ve dil paketleri gibi yerel ayarlara özgü bilgileri içerir.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<Package  
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
  Name="DisplayName"  
  Culture="Culture"  
  LicenseAgreement="eula.txt">  
  
  <PackageFiles>  
    <PackageFile Name="eula.txt"/>  
  </PackageFiles>  
  
  <Strings>  
    <String Name="DisplayName">Custom Bootstrapper Package</String>  
    <String Name="Culture">en</String>  
    <String Name="NotAnAdmin">You must be an administrator to install this package.</String>  
    <String Name="GeneralFailure">A general error has occurred while   
installing this package.</String>  
  </Strings>  
</Package>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ürün ve Paket Şema Başvurusu](../deployment/product-and-package-schema-reference.md)