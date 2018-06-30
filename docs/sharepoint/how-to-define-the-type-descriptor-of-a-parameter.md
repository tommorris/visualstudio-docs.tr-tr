---
title: 'Nasıl yapılır: bir parametrenin tür tanımlayıcısını tanımlama | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], type descriptor
- BDC [SharePoint development in Visual Studio], parameter types
- BDC [SharePoint development in Visual Studio], type descriptor
- Business Data Connectivity service [SharePoint development in Visual Studio], parameter types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d1709ea21fa785a573dae03ad8c89814c9952b50
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120435"
---
# <a name="how-to-define-the-type-descriptor-of-a-parameter"></a>Nasıl yapılır: bir parametrenin tür tanımlayıcısını tanımlama
  Bir tür tanımlayıcı bir parametre veri türünü tanımlayan özellikleri içerir. Bir tür tanımlayıcı alan, bir varlık veya bir varlıklar koleksiyonu tanımlayabilirsiniz. Daha fazla bilgi için bkz: [TypeDescriptor](http://msdn.microsoft.com/library/ms543392%28v=office.12%29.aspx).  
  
### <a name="to-define-the-type-descriptor-of-a-parameter"></a>Bir parametrenin tür tanımlayıcısını tanımlamak için  
  
1.  İçinde **BDC yöntem ayrıntıları** penceresinde, parametrenin tür tanımlayıcısını seçin.  
  
2.  Menü çubuğunda seçin **Görünüm**, **Özellikler penceresini**.  
  
3.  İçinde **özellikleri** penceresindeki tür tanımlayıcı özelliklerini ayarlayın.  
  
     Aşağıdaki yordamlar, bir tür tanımlayıcı alanı, varlık veya varlık koleksiyonu olarak tanımlamak açıklar.  
  
### <a name="to-define-a-field"></a>Bir alan tanımlamak için  
  
1.  İçinde **özellikleri** penceresindeki ayarlayın **adı** özellik türü tanımlayıcısı varlığı temsil eden Tür alanında adını (örneğin: **FirstName**).  
  
2.  İleri'listesinde **TypeName** özelliği, uygun veri türünü seçin (örneğin, **Int32**).  
  
     Diğer isteğe bağlı parametreler hakkında daha fazla bilgi için bkz: [TypeDescriptor](http://msdn.microsoft.com/library/ms543392%28v=office.12%29.aspx).  
  
### <a name="to-define-an-entity"></a>Bir varlık tanımlamak için  
  
1.  İçinde **özellikleri** penceresindeki ayarlayın **adı** varlığı tanımlayan bir ad özelliğine (örneğin: **kişi**).  
  
2.  Ayarlama **TypeName** özelliğini tam olarak nitelenmiş adına varlığı temsil eden tür. Bu tür bir sınıf projeniz, çözümünüzdeki başvuran bir derlemede tanımlanan bir türü veya BDC nesne modelinde tanımlanan bir türü olabilir.  
  
    -   Projenizdeki sınıfı için aşağı oka seçin **TypeName** özelliği seçin **geçerli projenin** sekmesinde görünür ve ardından projenizdeki sınıfı seçin iletişim kutusu.  
  
         Tam adı ad alanı ve LOB Sistem adından sınıfın adını içerir. Aşağıdaki örnek değerini ayarlar **TypeName** projenizdeki bir sınıf özelliğine.  
  
         `MyBDCNamespace.BdcModel1.Contact, BdcModel1`  
  
    -   Bir derlemeyi çözümünüzdeki bulunan bir türü için tam adı türünün adı, derleme, sürüm numarası, kültür ve ortak anahtar belirteci adını içerir.  
  
         Aşağıdaki örnek değerini ayarlar **TypeName** çözümünüzde başvuran bir derlemede tanımlanan bir türü için özellik.  
  
         `MyNamespace.Contact, myAssemblyName, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
    -   BDC nesne modelinde tanımlanan bir türü için tam adı ad alanı ve tür adını içerir.  
  
         Aşağıdaki örnek değerini ayarlar **TypeName** BDC nesne modelinde bir türe özelliği.  
  
         `Microsoft.BusinessData.Runtime.DynamicType`  
  
3.  İçinde **BDC yöntem ayrıntıları** penceresinde türü tanımlayıcısı görünen listesini açın ve ardından **Düzenle**.  
  
     **BDC Gezgini** penceresi açılır.  
  
4.  İçinde **BDC Gezgini**türü tanımlayıcısı kısayol menüsünü açın ve ardından **eklemek tür tanımlayıcı**.  
  
     Yeni bir tür tanımlayıcı varlık türü tanımlayıcısı için bir alt öğesi olarak eklenir. Bu tür tanımlayıcı alan olarak yapılandırın.  
  
5.  Varlık her bir alan için bir alt tür tanımlayıcı eklemek için 4. adımı yineleyin.  
  
### <a name="to-define-a-collection-of-entities"></a>Varlık koleksiyonu tanımlamak için  
  
1.  İçinde **BDC yöntem ayrıntıları** penceresinde istediğiniz parametrenin tür tanımlayıcısını seçin.  
  
2.  Menü çubuğunda seçin **Görünüm**, **Özellikler penceresini**.  
  
3.  İçinde **özellikleri** penceresindeki ayarlayın **adı** varlığı tanımlayan bir ad özelliğine (örneğin: **kişiler**).  
  
4.  Ayarlama **IsCollection** özelliğine **doğru**. Bu, bu tür tanımlayıcı bir varlıklar koleksiyonu olduğunu gösterir.  
  
5.  Ayarlama **TypeName** bir başvuru içeren bir dize özelliği <xref:System.Collections.Generic.IEnumerable%601> arabirimi ve varlığı temsil eden tür tam adı. Bu tür bir sınıf projeniz, çözümünüzdeki başvuran bir derlemede tanımlanan bir türü veya BDC nesne modelinde tanımlanan bir türü olabilir.  
  
    -   Projenizdeki sınıfı için aşağı oka seçin **TypeName** özelliği seçin **geçerli projenin** sekmesinde görünür ve ardından projenizdeki sınıfı seçin iletişim kutusu.  
  
         Tam adı ad alanı ve LOB Sistem adından sınıfın adını içerir.  
  
         Aşağıdaki örnek değerini ayarlar **TypeName** projenizdeki sınıfların bir koleksiyon özelliği.  
  
         `System.Collections.Generic.IEnumerable`1 [MyBDCNamespace.` ` BdcModel1.Contact, BdcModel1]'  
  
    -   Bir derlemeyi çözümünüzdeki bulunan bir türü için tam adı türünün adı, derleme, sürüm numarası, kültür ve ortak anahtar belirteci adını içerir.  
  
         Aşağıdaki örnek değerini ayarlar **TypeName** derlemedeki çözümünüzde başvuru türleri koleksiyonunu özelliğine.  
  
         `System.Collections.Generic.IEnumerable`1 [MyNamespace.Contact, myAssemblyName, sürüm 4.0.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089]'  
  
    -   BDC nesne modelinde tanımlanan bir türü için tam adı, yalnızca ad alanı ve tür adını içerir.  
  
         Aşağıdaki örnek değerini ayarlar **TypeName** özelliğini, bir BDC nesne modelinde tanımlı türler koleksiyonu.  
  
         `System.Collections.Generic.IEnumerable`1 [Microsoft.BusinessData.Runtime.DynamicType]'  
  
6.  İçinde **BDC yöntem ayrıntıları** penceresinde türü tanımlayıcısı görünen listesini açın ve ardından **Düzenle**.  
  
     **BDC Gezgini** penceresi açılır.  
  
7.  İçinde **BDC Gezgini**türü tanımlayıcısı kısayol menüsünü açın ve ardından **eklemek tür tanımlayıcı**.  
  
     Yeni bir tür tanımlayıcı koleksiyonu tür tanımlayıcı için bir alt öğesi olarak eklenir. Bu tür tanımlayıcı bir varlık olarak yapılandırın.  
  
## <a name="see-also"></a>Ayrıca bkz.
 [BDC modeli tasarım araçlarına genel bakış](../sharepoint/bdc-model-design-tools-overview.md)   
 [Nasıl yapılır: bir modele bir varlık ekleme](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [Nasıl yapılır: bir yönteme parametre ekleme](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Nasıl yapılır: yöntem örneği tanımlama](../sharepoint/how-to-define-a-method-instance.md)   
 [İş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
