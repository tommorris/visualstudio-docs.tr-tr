---
title: "Eski API kullanarak görünüm ayarlarını değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - changing view settings
ms.assetid: 12c9b300-0894-4124-96a1-764326176d77
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: dc68bf5f8a0e61b80200cd5454b78bcdda78cdfe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="changing-view-settings-by-using-the-legacy-api"></a>Eski API kullanarak görünüm ayarlarını değiştirme
Sözcük kaydırma, Seçim kenar boşluğu ve sanal adres alanı, gibi çekirdek Düzenleyicisi özellikleri için ayarları yoluyla kullanıcı tarafından değiştirilebilir **seçenekleri** iletişim kutusu. Ancak, aynı zamanda bu ayarları değiştirmek mümkündür programlı olarak.  
  
## <a name="changing-settings-by-using-the-legacy-api"></a>Eski API kullanarak ayarlarını değiştirme  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> Bir arabirimi kullanıma sunan bir metin Düzenleyicisi özellikleri kümesi. Metin görünümü metin görünümü için programlı olarak değiştirilen ayar grubu temsil eden bir kategori (GUID_EditPropCategory_View_MasterSettings) özelliklerini içerir. Görünüm ayarlarını bu şekilde değiştirilmiş sonra bunların içinde değiştirilemez **seçenekleri** sıfırlanana kadar iletişim kutusu.  
  
 Aşağıdaki çekirdek Düzenleyici örneği görünüm ayarlarını değiştirmek için tipik işlemidir.  
  
1.  Çağrı `QueryInterface` üzerinde (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>) için <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> arabirimi.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> için GUID_EditPropCategory_View_MasterSettings değerini belirten yöntemi `rguidCategory` parametresi.  
  
     Bunu yapmak için bir işaretçi döndürür <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> görünüm için zorunlu özellikler kümesini içeren arabirimi. Bu gruptaki tüm ayarları kalıcı olarak zorlanır. Bir ayar bu grupta yer almayan sonra belirtilen seçenekler izleyeceği **seçenekleri** iletişim kutusu veya kullanıcının komutları.  
  
3.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> yöntemi, uygun ayarları değeri belirterek `idprop` parametresi.  
  
     Örneğin, sözcük kaydırma zorlamak için arama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> ve VSEDITPROPID_ViewLangOpt_WordWrap, değerini belirtin `vt` için `idprop` parametresi. Bu çağrısında `vt` VT_BOOL türünde bir değişken olduğu ve `vt.boolVal` VARIANT_TRUE değil.  
  
## <a name="resetting-changed-view-settings"></a>Değiştirilen görünüm ayarlarını sıfırlama  
 Değişen tüm görünüm çekirdek Düzenleyici örneği için ayarını sıfırlamak için arama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> yöntemi ve uygun ayar değeri belirtin `idprop` parametresi.  
  
 Örneğin, sözcük kaydırma serbestçe float izin vermek için özellik kategoriden çağırarak kaldırmadan <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> ve VSEDITPROPID_ViewLangOpt_WordWrap için değeri belirterek `idprop` parametresi.  
  
 Değişen tüm ayarları çekirdek düzenleyici için aynı anda kaldırmak için VSEDITPROPID_ViewComposite_AllCodeWindowDefaults, vt için olan bir değer belirtin `idprop` parametresi. Bu çağrısında vt VT_BOOL türünde bir değişken ve vt.boolVal VARIANT_TRUE.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçinde çekirdek Düzenleyicisi](../extensibility/inside-the-core-editor.md)   
 [Eski API kullanarak getirip metin görünümü erişme](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)   
 [Seçenekler İletişim Kutusu](../ide/reference/options-dialog-box-visual-studio.md)