---
title: "Nasıl yapılır: CLR öznitelikleri bir öğede ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.EditAttributesDialog
helpviewer_keywords: Domain-Specific Language, custom attrributes
ms.assetid: b3db3c74-920c-4701-9544-6f75cbe8b7c9
caps.latest.revision: "19"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 7dcbd0005b80887dae91249a6781a6982414b9e5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
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
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)