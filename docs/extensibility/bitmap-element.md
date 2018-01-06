---
title: "Öğesi bit eşlem | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, Bitmaps
- Bitmaps element (VSCT XML schema)
ms.assetid: edcd7891-f4e7-416d-809d-5e2eed9f17e4
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: eb265aabdb4feda05512e036cda19abc574e2fd4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bitmap-element"></a>Bit eşlem öğesi
Bir bit eşlem tanımlar. Bit eşlem bir kaynaktan veya bir dosya yüklenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Bitmap guid="guidImages" href="images\MyImage.bmp" usedList="bmp1, bmp2, bmp3" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli. GUID/kimliği komut tanımlayıcı GUID.<br /><br /> Bir bit eşlem için GUID özniteliği herhangi VSPackage veya diğer komut grubu ile ilişkili değil.  Bit eşlem tanımına benzersiz olmalıdır ve başka bir amaçla kullanılmamalıdır.|  
|resID|GUID/kimliği komut tanımlayıcısı kimliği. ResID veya href özniteliği gereklidir.<br /><br /> ResID özniteliği komutu tablo birleştirme sırasında yüklenecek olan bit eşlem Şerit belirleyen bir tamsayı kaynak kimliğidir.  Komut tablo yüklenirken, kaynak Kimliğine göre belirtilen bit eşlemler aynı modülü kaynaktan yüklenecektir.|  
|usedList|ResID özniteliği mevcut ise gereklidir. Kullanılabilir görüntüler bit eşlem Şerit seçer.|  
|href|Bit eşlem yolu. ResID veya href özniteliği gereklidir.<br /><br /> Sonuçta elde edilen ikili katıştırılmış belirtilen yansıma dosyası için Include yolu aranır.  Komutu tablo birleştirme sırasında görüntünün kopyalanır ve ek kaynak arama ya da yük gereklidir.  Şerit tüm görüntüleri usedList özniteliği mevcut değilse kullanılabilir. **Not:** görüntüleri .bmp, .png ve .gif dahil birkaç biçimlerinden birinde sağlanabilir.  Derleyici önceki sürümlerinde, kısmi saydamlık alfa bilgilerine sahip 32-bit eşlem görüntülerini desteklemiyor. Bu sürümleri için geçici çözüm .png biçiminde kullanmaktır.|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Bitmaps Öğesi](../extensibility/bitmaps-element.md)|Bit eşlem öğeleri gruplandırır.|  
  
## <a name="example"></a>Örnek  
  
```  
<Bitmap guid="guidWidgetIcons" href="WidgetToolbarIcons_32.bmp" />  
<Bitmap guid="guidWidgetIcons2" resID="IDBMP_WIDGETICONS"  
  usedList="1, 2, 3, 4"/>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)