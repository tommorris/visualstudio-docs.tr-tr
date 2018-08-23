---
title: Kalıcılığı ve çalışmasını Belge tablosu | Microsoft Docs
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
- persistence, managing
- IVsPersistHierarchyItem interface, implementing
- architecture, persistence
- running document table (RDT), architecture
ms.assetid: 27117eae-6c58-4189-a61a-1397a43b5ecf
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 44f8025bd20fe6522ec0f835e299a2a9efd9ca1e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684534"
---
# <a name="persistence-and-the-running-document-table"></a>Kalıcılık ve Çalıştırılan Belge Tablosu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Kalıcılık ve çalıştırılan Belge tablosu](https://docs.microsoft.com/visualstudio/extensibility/internals/persistence-and-the-running-document-table).  
  
İçinde [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE, proje tamamen bunlar hizmetini kullanarak gerçekleştirmek, kendi proje öğelerinin Kalıcılık yönetmekten sorumlu <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>. Visual Studio ortamında Kalıcılık temel birimini belgelerdir. Proje açma, kaydetme ve çalıştırılan Belge tablosu (RDT), bütün açık belgeleri durumunu izleyen bir kaynak olan belgelerin yeniden adlandırma koordine edin.  
  
## <a name="managing-persistence"></a>Kalıcılık yönetme  
 Projelerini denetleyecek ortamın Kalıcılık hizmet uygulayarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem> arabirimi. Ortam hiçbir zaman doğrudan kendi kalıcı hale getirmek için bir belge ister, ancak sahip olan proje (veya hiyerarşi) belgeyi kaydetmek ister. Bu proje öğesi verisini yerel dosyaları, uzak dosyaları, bir veritabanı, bir depo veya diğer Orta kaydetmek için projeyi için mümkün kılar.  
  
 Genel ortam RDT tutar. Tüm açık pencereleri girişlerinde ortamı korur ve bunların kılar RDT belgelerde bir çözüm kapatıldığında gibi özel bildirimleri alın. Ayrıca, RDT, karşılık gelen düğümlerini izlemek ortam için mümkün kılar **Çözüm Gezgini**. Proje dosyaları hem proje öğesi belgeleri de dahil olmak üzere, açık, kalıcı nesne başına tek bir kayıtta RDT tutar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalıştırılan Belge tablosu](../../extensibility/internals/running-document-table.md)   
 [IDE’de Seçim ve Para Birimi](../../extensibility/internals/selection-and-currency-in-the-ide.md)

