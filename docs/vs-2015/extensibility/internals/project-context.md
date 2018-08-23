---
title: Proje bağlamı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], opening items
ms.assetid: d1803f4a-24eb-44b0-b5d2-cb40c15534be
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 280864c69e75d37c73095320787d74e61a93ab38
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686918"
---
# <a name="project-context"></a>Proje Bağlamı
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [proje bağlamı](https://docs.microsoft.com/visualstudio/extensibility/internals/project-context).  
  
Kullanıcı ekler veya projeleri ve proje öğeleri ile birlikte çalışır, IDE proje bağlam kavramı nasıl çeşitli işlemler gerçekleştirilmelidir belirlemek için kullanır.  
  
 Genellikle, dosyaları seçerek kullanıcı açıkça oluşturan standart proje nesnelerdir **yeni proje** komut veya seçerek kullanılabilir yapar **Proje Aç** komutunu  **Dosya** menüsü. Bu gibi durumlarda, dosyalar oluşturulur ve bir proje bağlamında açılır ve proje türü belge düzenleme bağlamı tanımlar.  
  
 Bazı projeler çok zengin bir bağlam sağlar. Örneğin, bir proje kapsamlı, programlı bir ad alanı veya proje kapsamlı veritabanı bağlantısı veri bağlama için proje yönetir. Kullanıcının sık dosyaları veya veritabanı bağlantıları görüntülenen Çözüm Gezgini'nde bir proje öğesi gibi bir özel Proje nesne kullanarak doğrudan açabilirsiniz.  
  
 Diğer zamanlarda ise, öğenin proje bağlamı açıkça belirtilmedi. Kullanıcı seçerek bir dosya açıldığında, örneğin, bir öğenin bağlam kullanılamıyor **mevcut Dosya Aç** komutunu **dosya** hata ayıklayıcıyı bir dosya veya kullanıcı tıkladığında çalıştığında menüsü **Dosyalarda Bul** komutunu **Bul ve Değiştir** iletişim kutusu. Bu durumlarda, IDE aramaları işlenecek <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument> bir belgeyi açmak için en iyi proje bulma işlemini yönetmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje önceliği](../../extensibility/internals/project-priority.md)   
 [Proje ve Proje Öğesi Şablonları Ekleme](../../extensibility/internals/adding-project-and-project-item-templates.md)

