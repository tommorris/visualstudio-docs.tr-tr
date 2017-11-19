---
title: "Çözümde dosyaları eklemeyi modüllerini kullanma | Microsoft Docs"
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
helpviewer_keywords:
- SharePoint development in Visual Studio, deployment modules
- SharePoint development in Visual Studio, modules
- modules [SharePoint development in Visual Studio]
ms.assetid: 74d1d69f-5cd9-452f-8d35-e1f4d8a084fd
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 484ae234839876922b6c04767d67ed56f85a108d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="using-modules-to-include-files-in-the-solution"></a>Çözüme Dosyaları Dahil Etmek için Modül Kullanma
  SharePoint server gibi yeni ana sayfalar kendi dosya türü ne olursa olsun dosyaları dağıtmak istediğinizde zamanlar olabilir. Bunu yapmak için kullanabileceğiniz *modülleri* (ile karıştırılmamalıdır [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] kod modülleri). Modüller, bir SharePoint çözüm dosyalarında kapsayıcılardır. Çözüm dağıtıldığında, modül dosyalarında SharePoint sunucusunda belirtilen klasörlerine kopyalanır.  
  
## <a name="module-items-and-elements"></a>Modül öğeleri ve öğeleri  
 Bir modül oluşturmak için bu projeye içinde seçerek eklemek **Yeni Öğe Ekle** iletişim kutusu. Ardından, kendi Elements.xml dosyasını sistemde nerede ve SharePoint sunucusuna kopyalanması gereken durumlarda, dağıtmak istediğiniz dosyaların adını içerecek şekilde değiştirin.  
  
 Aşağıda, bir modül Elements.xml dosyası örneği verilmiştir:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
    <Module Name="Module1">  
        <File Path="Module1\Sample.txt" Url="Module1/Sample.txt" />  
    </Module>  
</Elements>  
  
```  
  
 Yeni oluşturulan modüller aşağıdaki varsayılan dosyaları içerir:  
  
|Dosya Adı|Açıklama|  
|---------------|-----------------|  
|Elements.XML|Modül tanımı dosyası.|  
|Örnek.txt|Modül dosyasında bir örnek olarak hizmet veren bir yer tutucu dosyası.|  
  
 Elements.xml dosyası aşağıdaki öğeleri içerir:  
  
|Öğe adı|Açıklama|  
|------------------|-----------------|  
|Öğeleri|Modülde tanımlanan tüm öğeleri içerir.|  
|Modül|Modül öğesi tek bir özniteliği var *adı*, modül adı biçiminde belirtir `<Module Name="Module1">`.<br /><br /> Modülün adını değiştirirseniz unutmayın (veya kendi *klasör adı* özelliği), modül öğesindeki adla el ile güncelleştirmeniz gerekir.<br /><br /> Dosya veya dosyalar için bir alt modülü öğesinde belirtirseniz, [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] (WSS) otomatik olarak oluşturacak eşleşen bir dizin yapısına kendileri için.|  
|Dosya|Dosya öğesi iki parametreye sahip *yolu* ve *Url*.<br /><br /> -Path: Adını ve konumunu SharePoint çözüm dosyasında. Biçimidir, `Path="Module1\Sample.txt"`.<br /><br /> -Url: SharePoint sunucusu üzerinde dosya dağıtılacağı konumu. Biçimidir, `Url="Module1/Sample.txt"`.<br /><br /> -Type: iki ayarlara sahip bir isteğe bağlı öznitelik: *GhostableInLibrary* ve *Ghostable*. Biçimidir, `Type="GhostableInLibrary"`. Belirtme *GhostableInLibrary* dosya, SharePoint belge kitaplığında kitaplığa eklendiğinde dosya eşlik için bir liste öğesi ile birlikte eklenir anlamına gelir. Belirtme *Ghostable* belge kitaplığı dışında SharePoint'e eklenecek dosyanın neden olur.|  
  
 Dağıtmak istediğiniz her dosya için ayrı bir gerekli `<File>` Elements.xml öğe girişi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir modül kullanarak dosyaları dahil etme](../sharepoint/how-to-include-files-by-using-a-module.md)   
 [nasıl yapılır: bir dosya sağlama](http://go.microsoft.com/fwlink/?LinkID=144271)   
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint için Web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Paketleme ve SharePoint çözümlerini dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  