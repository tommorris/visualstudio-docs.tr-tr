---
title: "Komut işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - command handling
ms.assetid: 78f67d92-77f7-45cb-ad75-6e3346379cc3
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0cb2bf52c038b0abbac742aafa942f2f7ea7ea1d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="command-handling"></a>Komut işleme
Düzenleyicinizi yeni komutlar tanımlayabilirsiniz. Komutlar, genellikle bir araç çubuğundaki ya da bir bağlam menüsündeki menüsünde görüntülenir.  
  
 Komutlar ve menüleri tanımlama hakkında daha fazla bilgi için bkz: [komutları, menüleri ve araç çubuklarını](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Bir dil hizmeti uğratarak Düzenleyicisi'nde gösterilen hangi bağlam menülerini denetleyebilirsiniz <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> numaralandırması. Alternatif olarak, bağlam menüsü işaret başına temelinde kontrol edebilirsiniz. Daha fazla bilgi için bkz: [dil hizmeti filtreleri için önemli komutları](../extensibility/internals/important-commands-for-language-service-filters.md).  
  
## <a name="adding-commands-to-the-editor-context-menu"></a>Düzenleyici bağlam menüsüne komut ekleme  
 Bağlam menüsüne bir komut eklemek için önce bir dizi menü komutları belirli bir gruba ait tanımlamanız gerekir. Aşağıdaki örnek, izlenecek bir parçası olarak oluşturulan .vsct dosyanın alındığı [izlenecek yol: ekleme özellikleri için bir özel düzenleyici](../extensibility/walkthrough-adding-features-to-a-custom-editor.md):  
  
 \<Menü GUID = "guidCustomEditorCmdSet" id = "IDMX_RTF" öncelik = "0x0000" type = "Context" >  
  
 \<Üst GUID = "guidCustomEditorCmdSet" id = "0" / >  
  
 \<Dize >  
  
 \<■ ButtonText > CustomEditor bağlam menüsü\</ButtonText >  
  
 \<CommandName > CustomEditorContextMenu\</CommandName >  
  
 \</ Dizeleri >  
  
 \</ Menü >  
  
 \</ Menülerine >  
  
 Yukarıdaki metni metin bağlam menüsü komutuyla ekler **CustomEditor bağlam menüsü**. Menü komut kümesini bu Düzenleyicisi ile oluşturulur ve "Context" türüdür GUID'dir.  
  
 Ayrıca .vsct dosyasında tanımlanmış gerekmez önceden tanımlanmış komutlarını da kullanabilirsiniz. Visual Studio Paketi şablonu tarafından oluşturulan EditorPane.cs dosyanın incelerseniz, örneğin, bir dizi önceden tanımlanmış komut gibi bulduğunuz <xref:Microsoft.VisualStudio.VSConstants.VSStd97CmdID> tarafından tanımlanan <xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>, komut işleyicileri onSelectAll yöntemi gibi işlenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komutları, menüleri ve araç çubukları](../extensibility/internals/commands-menus-and-toolbars.md)