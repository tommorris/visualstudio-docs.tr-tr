---
title: "Kalıcılığı ve çalışmasını belge tablo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- persistence, managing
- IVsPersistHierarchyItem interface, implementing
- architecture, persistence
- running document table (RDT), architecture
ms.assetid: 27117eae-6c58-4189-a61a-1397a43b5ecf
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 062c623ec1de779733e41a8abcad8ca478155dba
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="persistence-and-the-running-document-table"></a>Kalıcılığı ve çalışan belge tablosu
İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE projeleri bunlar hizmet kullanarak gerçekleştirmek, kullanıcıların proje öğeleri kalıcılığı yönetmek için tamamen sorumlu <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>. Visual Studio ortamında Kalıcılık temel birimidir belgelerdir. Proje açma, kaydetme ve çalışan belge tablosu (RDT), tüm açık belgeleri durumunu izleyen bir kaynak belgelerle adlandırılmasını koordine.  
  
## <a name="managing-persistence"></a>Kalıcılık yönetme  
 Projeleri uygulayarak ortamı Kalıcılık Hizmet Denetim <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem> arabirimi. Ortam hiçbir zaman doğrudan kendisini kalıcı hale getirmek için bir belge ister olsa da, sahibi olan proje (veya hiyerarşi) belgeyi kaydetmek için sorar. Proje öğesi verilerini yerel dosyaları, uzak dosyaları, bir veritabanı, bir havuz veya diğer Orta kaydetmek için projeyi olanaklı kılar.  
  
 Genel ortam RDT tutar. Tüm açık pencereleri girişlerinde ortamı tutar ve bunların kılar RDT belgelerde bir çözüm kapatıldığında gibi özel bildirimleri alma. Ayrıca, RDT, karşılık gelen düğümlerini izlemek ortamı için mümkün kılar **Çözüm Gezgini**. RDT açık, kalıcı nesne proje dosyalarını ve proje öğesi belgeleri de dahil olmak üzere, her bir kayıt tutar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışan belge tablosu](../../extensibility/internals/running-document-table.md)   
 [Seçim ve IDE içinde para birimi](../../extensibility/internals/selection-and-currency-in-the-ide.md)