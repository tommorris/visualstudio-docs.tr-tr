---
title: 'Nasıl yapılır: ekleme ve kaldırma ek derlemeler | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.CustomAssembly
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cadfffb2dbf977e23a0edb082065125aea4f5940
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-and-remove-additional-assemblies"></a>Nasıl yapılır: Ek Derlemeler Ekleme ve Kaldırma
  İşlev veya veri için diğer derlemeleri SharePoint paketi bağımlı olması durumunda, çözüm paketinizi (.wsp) derlemelerini ekleyebilirsiniz. Bu şekilde, SharePoint server özel derlemeler bir paket zaten yüklü olduğundan emin hale getirir.  
  
 Ayrıca, ekleyin ve güvenli denetimler ve derlemeler ile ilişkilendirilmiş sınıf kaynak dosyaları değiştirin.  
  
## <a name="adding-additional-assemblies-safe-controls-and-class-resources"></a>Ek derlemeler, güvenli denetimler ve sınıfı kaynakları ekleme  
 SharePoint çözüm paketi ek derlemelerine ekleyebilirsiniz. Korumalı bir çözümde ek derlemeleri genel derleme önbelleğine dağıtma, ancak SharePoint Proje öğeleri korumalı bir çözümde içerik veritabanına eklenir. Güvenli denetimler ve sınıfı kaynakları'nı, ayrıca bu ek derlemeler ekleyebilirsiniz. Güvenli denetimler hakkında daha fazla bilgi için bkz: [sağlama paketleme ve dağıtım bilgileri proje öğelerinde](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) ya da "Oluşturma bir SafeControl girişinde" [Web Bölümleri SharePoint Foundation dağıtma](http://go.microsoft.com/fwlink/?LinkId=245505).  
  
#### <a name="to-add-an-existing-assembly"></a>Varolan bir derleme eklemek için  
  
1.  Açık **paketini Tasarımcısı**. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint çözüm paketini özelleştirme](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).  
  
2.  Seçin **Gelişmiş** sekmesi.  
  
3.  Seçin **Ekle** düğmesine tıklayın ve ardından **varolan derleme Ekle** listeden.  
  
     **Varolan derleme Ekle** iletişim kutusu görüntülenir.  
  
4.  Üç nokta seçin (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP.NET Mobil Tasarımcı elips")) ve ardından eklemek istediğiniz derleme seçin. Seçili derlemenin göreli bir yol taşınabilirlik amacıyla kullanmanızı öneririz.  
  
5.  İçin **dağıtım hedef**, seçin **GlobalAssemblyCache** derlemeyi genel derleme önbelleğine dağıtmanız veya seçmek için seçenek düğmesi **WebApplication** seçeneği SharePoint çalıştıran sunucu üzerindeki WebApplication klasöre derlemesi dağıtmak için düğmesi.  
  
#### <a name="to-add-an-assembly-from-project-output"></a>Proje çıktısından bir derleme eklemek için  
  
1.  Açık **paketini Tasarımcısı**.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint çözüm paketini özelleştirme](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).  
  
2.  Seçin **Gelişmiş** sekmesi.  
  
3.  Seçin **Ekle** düğmesine tıklayın ve ardından **proje çıktısından derleme Ekle** listeden.  
  
     **Proje çıktısından derleme Ekle** iletişim kutusu görüntülenir.  
  
4.  İçinde **kaynak proje** listesinde ve eklemek istediğiniz kaynak projesini seçin.  
  
5.  İçin **dağıtım hedef**, seçin **GlobalAssemblyCache** derlemeyi genel derleme önbelleğine dağıtmanız veya seçmek için seçenek düğmesi **WebApplication** seçeneği SharePoint çalıştıran sunucu üzerindeki WebApplication klasöre derlemesi dağıtmak için düğmesi.  
  
#### <a name="to-add-a-safe-control"></a>Güvenli bir denetim eklemek için  
  
1.  Açık **Düzenle varolan derleme** iletişim kutusu. Bunu başarmak için paket tasarımcısını açın, seçin **Gelişmiş** sekmesinde, bir derlemeyi seçin ve ardından **Düzenle**düğmesi.  
  
2.  İçinde **güvenli denetimler** bölmesinde seçin **yeni öğe eklemek için burayı tıklatın** düğmesi.  
  
3.  İçinde **derleme adı** sütunu derlemenin adını girin.  
  
4.  İçinde **Namespace** sütun, güvenli denetimi ad alanı adını girin.  
  
5.  İçinde **türü adı** sütun türünün adını girin.  
  
#### <a name="to-add-a-class-resource"></a>Bir sınıf kaynak eklemek için  
  
1.  Açık **Düzenle varolan derleme** iletişim kutusu. Bunu başarmak için paket tasarımcısını açın, seçin **Gelişmiş** sekmesinde, bir derlemeyi seçin ve ardından **Düzenle** düğmesi.  
  
2.  İçinde **sınıfı kaynakları** bölmesinde seçin **yeni öğe eklemek için burayı tıklatın** düğmesi.  
  
3.  İçinde **dosya adı** sütun, üç nokta seçin (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP.NET Mobil Tasarımcı elips")) ve eklemek istediğiniz sınıfı kaynağı seçin.  
  
## <a name="deleting-custom-assemblies"></a>Derlemeleri silme  
 Bir SharePoint paketinden derlemeleri silin veya güvenli denetimler ve sınıfı kaynakları mevcut derlemelerden silin.  
  
#### <a name="to-delete-an-existing-assembly"></a>Varolan bir derlemeyi silmek için  
  
1.  Açık **paketini Tasarımcısı**. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint çözüm paketini özelleştirme](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).  
  
2.  Seçin **Gelişmiş** sekmesi.  
  
3.  İçinde **ek derlemeler** bölmesinde, silmek istediğiniz özel bir derlemeyi seçin.  
  
4.  Seçin **silmek** düğmesi.  
  
#### <a name="to-delete-a-safe-control-for-an-assembly"></a>Güvenli bir denetim için bir derleme silmek için  
  
1.  Açık **Düzenle varolan derleme** iletişim kutusu. Bunu başarmak için paket tasarımcısını açın, seçin **Gelişmiş** sekmesinde, bir derlemeyi seçin ve ardından **Düzenle** düğmesi.  
  
2.  Silmek istediğiniz güvenli denetimi seçin.  
  
3.  Delete anahtar seçin.  
  
#### <a name="to-delete-a-class-resource-for-an-assembly"></a>Bir derleme için bir sınıf kaynak silmek için  
  
1.  Açık **Düzenle varolan derleme** iletişim kutusu. Bunu başarmak için paket tasarımcısını açın, seçin **Gelişmiş** sekmesinde, bir derlemeyi seçin ve ardından **Düzenle** düğmesi.  
  
2.  Silmek istediğiniz sınıfı kaynak seçin.  
  
3.  Delete anahtar seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint özellikleri oluşturma](../sharepoint/creating-sharepoint-features.md)   
 [Nasıl yapılır: bir SharePoint özelliğini özelleştirme](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [Nasıl yapılır: SharePoint Özelliklerine Öğe Ekleme ve Kaldırma](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)   
  
  