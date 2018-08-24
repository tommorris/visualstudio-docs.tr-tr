---
title: Kullanarak yalıtılmış Kabuğu değiştirme. Vsct dosya | Microsoft Docs
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
- Visual Studio shell, isolated mode%2C .vsct file
ms.assetid: 6d147c2d-10e9-400e-b8ce-5566287b41ba
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0606d28f151f0d9c85980121e3129bd9204c61b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696044"
---
# <a name="modifying-the-isolated-shell-by-using-the-vsct-file"></a>Kullanarak yalıtılmış Kabuğu değiştirme. Vsct dosyası
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yalıtılmış Kabuğu kullanarak değiştirme. Vsct dosya](https://docs.microsoft.com/visualstudio/extensibility/modifying-the-isolated-shell-by-using-the-dot-vsct-file).  
  
UI proje bir Visual Studio yalıtılmış Kabuğu projesi için hangi uygulama grupları ve tek tek komutlarla uygulamada kullanılabilir olduğunu belirlemenizi sağlayan .vsct dosyası içerir. Değiştirilmemiş .vsct dosyası kitabından verilmiştir.  
  
```  
<!-- <Define name="No_WindowListCommand"/> -->  
<!-- <Define name="No_MoreWindowsCommand"/> -->  
<!-- <Define name="No_PaneNextPaneCommand"/> -->  
<!-- <Define name="No_PanePrevPaneCommand"/> -->  
```  
  
 Varsayılan olarak, çoğu komutları ve komut grupları dahil edilir. Bir komut veya komut grubuyla tutmak için yalnızca söz konusu komut veya Grup açıklamasını kaldırın.  
  
 Örneğin, önceki bölmesi komutları ve sonraki bölme kaldırmak için açıklama durumundan çıkarın `No_PaneNextPaneCommand` ve `No_PanePrevPaneCommand` girişleri:  
  
```  
  
<Define name="No_PaneNextPaneCommand"/> <Define name="No_PanePrevPaneCommand"/>  
  
```  
  
 Bu özelleştirmeler örnek daha ayrıntılı için bkz: [izlenecek yol: temel yalıtılmış Kabuk uygulaması oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
## <a name="referenced-files"></a>Başvurulan dosyaları  
 Bir uygulama için varsayılan .vsct dosyası aşağıdaki dosyaları başvuruyor. Bu dosyalar Visual Studio SDK yükleme dizini \VisualStudioIntegration\Common\Inc\ alt dizinde bulunur.  
  
|Dosya|Açıklama|  
|----------|-----------------|  
|wbids.h|Web'de gezinmek paket için kullanıcı Arabirimi kimlikleri.|  
|AppIDCmdUsed.vsct|Komut tablosu birincil Visual Studio kullanıcı Arabirimi öğeleri için.|  
|EmulatorCmdUsed.vsct|Emacs ve kısa Düzenleyicisi öykünmesi kullanıcı Arabirimi öğeleri için komut tablosu.|  
|Vsdebugguids.h|Komutlar, Seçenekler sayfası ve diğer özellikleri Visual Studio hata ayıklayıcının GUID'leri tanımlar.|  
|VsDbgCmdUsed.vsct|Hata ayıklayıcının komut tablosu.|  
  
 Visual Studio UI öğelerini uygulama .vsct dosyası içinde tanımlanan simgeleri göre AppIDCmdUsed.vsct dosyası içerir.  
  
 Daha fazla bilgi için [tasarlama XML komut tablosu (. Vsct) dosyaları](../extensibility/internals/designing-xml-command-table-dot-vsct-files.md) ve [VSCT XML Şeması Başvurusu](../extensibility/vsct-xml-schema-reference.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Yalıtılmış Kabuğu](../extensibility/visual-studio-isolated-shell.md)

