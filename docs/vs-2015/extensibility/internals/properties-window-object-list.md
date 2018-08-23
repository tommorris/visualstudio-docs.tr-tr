---
title: Özellikler penceresi nesne listesi | Microsoft Docs
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
- Properties window, object list
ms.assetid: 6c159c9d-345d-4b23-8ddd-9839d338b62f
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 87592deaec57b5638336cf191f12896cccbcb5b3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687549"
---
# <a name="properties-window-object-list"></a>Özellikler Penceresi Nesne Listesi
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Özellikler penceresi nesne listesi](https://docs.microsoft.com/visualstudio/extensibility/internals/properties-window-object-list).  
  
Nesne listesinde **özellikleri** bir veya daha fazla seçili pencereleri içinde kullanılabilir olan diğer nesnelerin seçimini değiştirmek izin veren bir açılır listede bir penceredir. Bu listede farklı bir nesne seçmek için bir çağrı tetikler <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A> yeni bir nesne seçili ortam bildirmek için. Görüntülenen bilgileri **özellikleri** penceresi yeni seçilen bir nesneyle ilişkili özellikleri görüntülemek için sonra değiştirilir.  
  
## <a name="the-object-list"></a>Nesne listesi  
 Nesne listesine iki alandan oluşur: nesne adı (kalın olarak gösterilir) ve nesne türü.  
  
 Soldaki kalın nesne türü için görüntülenen nesne adı nesnesinden alınır kullanarak `Name` özelliği tarafından sağlanan <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> arabirimi. <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo.GetClassInfo%2A>, yalnızca metottaki <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, döndürür <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo> o arabirimin coclass'ı için. **Özellikleri** penceresi kullanan <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> aşağı açılan listesinde nesne adı olarak gösterilen coclass adı.  
  
 Nesne yoksa bir `Name` özelliği, bir ad nesne listesinin adı alanında görüntülenmez. Nesne listesinde görüntülenen adını isterseniz nesnesine Name özelliği ekleyebilirsiniz.  
  
 COM nesnesi uygulamazsa <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, **özellikleri** penceresinde, listenin sol tarafında arabirim adını nesne adının yerine görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellikleri Genişletme](../../extensibility/internals/extending-properties.md)

