---
title: "Nasıl yapılır: CLR öznitelikleri bir öğede ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 1eedf41931c7f9476691e507ab0afcd9e2a4c4ee
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>Nasıl yapılır: Bir Öğede CLR Özniteliklerini Ayarlama
Etki alanı öğeleri, şekiller, bağlayıcılar ve diyagramları için eklenen özel öznitelikler özel öznitelikleridir. Öğesinden devralınan herhangi bir öznitelik ekleyebilirsiniz `System.Attribute` sınıfı.  
  
### <a name="to-add-a-custom-attribute"></a>Özel bir öznitelik eklemek için  
  
1.  İçinde **DSL Explorer**, özel bir öznitelik eklemek istediğiniz öğeyi seçin.  
  
2.  İçinde **özellikleri** penceresinde, sonraki **özel öznitelikleri** özelliği, Gözat'ı (**...** ) simgesi.  
  
     **Öznitelikleri Düzenle** iletişim kutusu açılır.  
  
3.  İçinde **adı** sütun tıklatın  **\<öznitelik Ekle >** ve, öznitelik adı yazın. ENTER tuşuna basın.  
  
4.  Öznitelik adı altında satır parantez gösterir. Bu satırda parametre özniteliği için yazın (örneğin, `string`), ve ardından ENTER tuşuna basın.  
  
5.  İçinde **Name özelliği** sütun, uygun bir ad yazın, örneğin, `MyString`.  
  
6.  **Tamam**'ı tıklatın.  
  
     **Özel öznitelikleri** özelliği şimdi özniteliği şu biçimde görüntüler:  
  
     `[`*AttributeName* `(` *ParameterName* `=` *türü*`)]`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)