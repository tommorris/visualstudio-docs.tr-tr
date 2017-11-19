---
title: "Seçenekler sayfası, yazı tipleri ve renkler düğümü özellikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tools Options settings, Fonts and Colors node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 8e1ab784-5f85-4e2b-8ef9-e5d59ca4dbcb
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0c2618dbaad3fcae95219e2b6a8a1f9b3d87bf09
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="options-page-fonts-and-colors-node-properties"></a>Seçenekler Sayfası, Yazı Tipleri ve Renkler Düğümü Özellikleri
Yazı tipi ve renk özellikleri altında görünmesi kayıtlı bir araç penceresi için bu belgede açıklanan **yazı tiplerini ve renkleri** içinde **ortam** kategorisini **seçenekleri** iletişim kutusu. Bu öğelerin VSPackages yüklediyseniz veya değiştirebilirsiniz colorable, grupları dinamik yapısını destekler.  
  
 Aşağıdaki bölümde kayıtlı penceresi türü ve her penceresi için kullanılabilir olan özellikleri örneği gösterilmektedir.  
  
## <a name="text-editor-or-printer-or-dialogs-and-tool-windows"></a>Metin Düzenleyicisi veya yazıcı veya iletişim kutuları ve araç pencereleri  
 `DTE.Properties("FontsAndColors", "TextEditor")`  
  
 veya  
  
 `DTE.Properties("FontsAndColors", "Printer")`  
  
 veya  
  
 `DTE.Properties("FontsAndColors", "Dialogs and Tool Windows")`  
  
|Özellik Öğesi Adı|Değer|Açıklama|  
|------------------------|-----------|-----------------|  
|FontFamily|Get/Set (dize)|"Courier gibi yeni." kullanılacak yazı tipi adı|  
|FontCharacterSet|Get/Set (<xref:EnvDTE.vsFontCharSet>)|A <xref:EnvDTE.vsFontCharSet> İbranice veya Rusça gibi kullanmak üzere ayarlanmış karakter türünü belirten değer.|  
|FontSize|Get/Set (kısa)|Noktaları kullanılacak yazı tipi boyutu. Örneğin, 10 veya 12.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçeneklerini denetleme](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Seçenekler sayfalarında özellik öğelerinin adlarını belirleme](http://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Seçenekler sayfası, ortam düğümü özellikleri](../../ide/reference/options-page-environment-node-properties.md)   
 [Seçenekler sayfası, metin düzenleyici düğümü özellikleri](../../ide/reference/options-page-text-editor-node-properties.md)