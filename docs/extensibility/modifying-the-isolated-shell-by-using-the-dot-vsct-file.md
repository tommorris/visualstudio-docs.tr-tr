---
redirect_url: shell/modifying-the-isolated-shell-by-using-the-dot-vsct-file
title: "Yalıtılmış Kabuk kullanarak değiştirme. Vsct dosya | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode, .vsct file
ms.assetid: 6d147c2d-10e9-400e-b8ce-5566287b41ba
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3290e33ac473c6914437f8ef036ec8047f46e063
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="modifying-the-isolated-shell-by-using-the-vsct-file"></a>Yalıtılmış Kabuk kullanarak değiştirme. Vsct dosyası
UI proje bir Visual Studio yalıtılmış Kabuk projesi için hangi uygulama grupları ve tek tek komutlar uygulamada kullanılabilir belirtmenize olanak sağlar. bir .vsct dosyası içerir. Değiştirilmemiş .vsct dosyasından bir Alıntısı verilmiştir.  
  
```  
<!-- <Define name="No_WindowListCommand"/> -->  
<!-- <Define name="No_MoreWindowsCommand"/> -->  
<!-- <Define name="No_PaneNextPaneCommand"/> -->  
<!-- <Define name="No_PanePrevPaneCommand"/> -->  
```  
  
 Varsayılan olarak, çoğu komutları ve komut grupları dahil edilir. Bir komut veya komut grubu dışlamak için yalnızca o komut veya grup açıklamadan çıkarın.  
  
 Örneğin, önceki bölmesi komutları ve sonraki bölme kaldırmak için açıklamadan çıkarın `No_PaneNextPaneCommand` ve `No_PanePrevPaneCommand` girişleri:  
  
```  
  
<Define name="No_PaneNextPaneCommand"/> <Define name="No_PanePrevPaneCommand"/>  
  
```  
  
 Bu özelleştirmeler örnek daha ayrıntılı için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
## <a name="referenced-files"></a>Başvurulan dosyaları  
 Bir uygulama için varsayılan .vsct dosyası aşağıdaki dosyaları başvurur. Bu dosyalar Visual Studio SDK yükleme dizininin \VisualStudioIntegration\Common\Inc\ alt bulunur.  
  
|Dosya|Açıklama|  
|----------|-----------------|  
|wbids.h|UI kimlikleri Web'e göz atmak paket için.|  
|AppIDCmdUsed.vsct|Birincil Visual Studio kullanıcı Arabirimi öğeleri tablosu komutu.|  
|EmulatorCmdUsed.vsct|Emacs ve kısa Düzenleyicisi öykünme kullanıcı Arabirimi öğeleri tablosu komutu.|  
|Vsdebugguids.h|Komutları, Seçenekler sayfası ve diğer Visual Studio hata ayıklayıcısı özelliklerini GUID'lerini tanımlar.|  
|VsDbgCmdUsed.vsct|Hata ayıklayıcı tablosu komutu.|  
  
 AppIDCmdUsed.vsct dosya uygulama .vsct dosyasında tanımlanmış semboller göre Visual Studio kullanıcı Arabirimi öğeleri içerir.  
  
 Daha fazla bilgi için bkz: [XML komutu tablosu tasarlama (. Vsct) dosyaları](../extensibility/internals/designing-xml-command-table-dot-vsct-files.md) ve [VSCT XML Şeması Başvurusu](../extensibility/vsct-xml-schema-reference.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio yalıtılmış Kabuk](../extensibility/visual-studio-isolated-shell.md)