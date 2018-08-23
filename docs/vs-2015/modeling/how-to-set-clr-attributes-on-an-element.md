---
title: 'Nasıl yapılır: bir öğede CLR özniteliklerini ayarlama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
ms.assetid: b3db3c74-920c-4701-9544-6f75cbe8b7c9
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: afcbadd7c7b3a18c94228e7221eda32b7117a2ed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632316"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>Nasıl yapılır: Bir Öğede CLR Özniteliklerini Ayarlama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: bir öğede CLR özniteliklerini ayarlama](https://docs.microsoft.com/visualstudio/modeling/how-to-set-clr-attributes-on-an-element).  
  
Özel öznitelikler, etki alanı öğeleri, şekiller, bağlayıcılar ve diyagramları için eklenen özel öznitelikler bağlıdır. Devralınan herhangi bir öznitelik ekleyebilirsiniz `System.Attribute` sınıfı.  
  
### <a name="to-add-a-custom-attribute"></a>Özel bir öznitelik eklemek için  
  
1.  İçinde **DSL Gezgini**, özel bir öznitelik eklemek istediğiniz öğeyi seçin.  
  
2.  İçinde **özellikleri** penceresi, sonraki **özel öznitelikler** özelliği, Gözat'a tıklayın (**...** ) simgesi.  
  
     **Düğmeye tıklandığında öznitelikleri Düzenle** iletişim kutusu açılır.  
  
3.  İçinde **adı** sütun tıklayın  **\<öznitelik Ekle >** , öznitelik adı yazın. ENTER tuşuna basın.  
  
4.  Öznitelik adı altında satırın parantez gösterir. Parametre türü özniteliği için bu satıra yazın (örneğin, `string`), ve ardından ENTER tuşuna basın.  
  
5.  İçinde **Name özelliği** sütun, uygun bir ad yazın örneğin, `MyString`.  
  
6.  **Tamam**'ı tıklatın.  
  
     **Özel öznitelikler** özelliği artık şu biçimde öznitelik görüntüler:  
  
     `[` *AttributeName* `(` *ParameterName* `=` *türü* `)]`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



