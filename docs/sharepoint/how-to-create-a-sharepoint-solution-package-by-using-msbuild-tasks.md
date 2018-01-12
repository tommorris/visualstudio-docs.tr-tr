---
title: "Nasıl yapılır: MSBuild görevlerini kullanarak bir SharePoint çözüm paketi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, packages
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 210793ab224e4da324591780dd3e6b171a1d721a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks"></a>Nasıl yapılır: MSBuild Görevlerini Kullanarak bir SharePoint Çözüm Paketi Oluşturma
  Yapı, temizleme ve geliştirme bilgisayarındaki komut satırı MSBuild görevlerini kullanarak bir SharePoint paketi (.wsp) doğrulama. Bu komutlar, yapı işlemi bir yapı bilgisayarında Team Foundation Server kullanarak otomatik hale getirmek için de kullanabilirsiniz.  
  
## <a name="building-a-sharepoint-package"></a>Bir SharePoint paketi oluşturma  
  
#### <a name="to-build-a-sharepoint-package"></a>Bir SharePoint paketi oluşturmak için  
  
1.  Windows **Başlat** menüsünde seçin **tüm programlar**, **Donatılar**, **komut istemi**.  
  
2.  SharePoint Proje bulunduğu dizine geçin.  
  
3.  Proje için bir paket oluşturmak için aşağıdaki komutu girin. Değiştir *ProjectFileName* proje adı.  
  
    ```  
    msbuild /t:Package ProjectFileName  
    ```  
  
     Örneğin, ListDefinition1 adlı bir SharePoint Proje paketlemek için aşağıdaki komutlardan birini çalıştırabilirsiniz.  
  
    ```  
    msbuild /t:Package ListDefinition1.vbproj  
    msbuild /t:Package ListDefinition1.csproj  
    ```  
  
## <a name="cleaning-a-sharepoint-package"></a>Bir SharePoint Paketi temizleme  
  
#### <a name="to-clean-a-sharepoint-package"></a>Bir SharePoint paketi temizlemek için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  SharePoint Proje bulunduğu dizine geçin.  
  
3.  Proje için bir paket temizlemek için aşağıdaki komutu girin. Değiştir *ProjectFileName* proje adı.  
  
    ```  
    msbuild /t:CleanPackage ProjectFileName  
    ```  
  
     Örneğin, ListDefinition1 adlı bir SharePoint Proje temizlemek için aşağıdaki komutlardan birini çalıştırabilirsiniz.  
  
    ```  
    msbuild /t:CleanPackage ListDefinition1.vbproj  
    msbuild /t:CleanPackage ListDefinition1.csproj  
    ```  
  
## <a name="validating-a-sharepoint-package"></a>Bir SharePoint paketi doğrulama  
  
#### <a name="to-validate-a-sharepoint-package"></a>Bir SharePoint paketi doğrulamak için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  SharePoint Proje bulunduğu dizine geçin.  
  
3.  Proje için bir paket doğrulamak için aşağıdaki komutu girin. Değiştir *ProjectFileName* proje adı.  
  
    ```  
    msbuild /t:ValidatePackage ProjectFileName  
    ```  
  
     Örneğin, ListDefinition1 adlı bir SharePoint Proje doğrulamak için aşağıdaki komutlardan birini çalıştırabilirsiniz.  
  
    ```  
    msbuild /t:ValidatePackage ListDefinition1.vbproj  
    msbuild /t:ValidatePackage ListDefinition1.csproj  
    ```  
  
## <a name="setting-properties-in-a-sharepoint-package"></a>Bir SharePoint paket özelliklerini ayarlama  
  
#### <a name="to-set-a-property-in-a-sharepoint-package"></a>Bir SharePoint pakette bir özelliği ayarlamak için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  SharePoint Proje bulunduğu dizine geçin.  
  
3.  Proje için bir paketteki bir özelliği ayarlamak için aşağıdaki komutu girin. Değiştir *PropertyName* ayarlamak istediğiniz özelliğine sahip.  
  
    ```  
    msbuild /property:PropertyName=Value  
    ```  
  
     Örneğin, uyarı düzeyini ayarlamak için aşağıdaki komutu çalıştırabilirsiniz.  
  
    ```  
    msbuild /property:WarningLevel = 2  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint özellikleri oluşturma](../sharepoint/creating-sharepoint-features.md)   
 [Nasıl yapılır: bir SharePoint özelliğini özelleştirme](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [Nasıl yapılır: SharePoint Özelliklerine Öğe Ekleme ve Kaldırma](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
  
  