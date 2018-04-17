---
title: Genişletme ve aracı Windows özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- user interfaces, essentials
- tool windows, standard
ms.assetid: 46b2892e-7b2b-4b3f-83a7-b884f1e114ee
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2ef4f656ed7b7ab7facbcfb470fca98327276cce
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="extending-and-customizing-tool-windows"></a>Genişletme ve aracı Windows özelleştirme
Visual Studio, windows, örneğin aracı windows, belge pencereleri ve iletişim windows birkaç farklı türde sağlar. Özellikler penceresi, çıktı penceresi ve Görev Listesi penceresi gibi diğer windows aracı windows türleridir.  
  
## <a name="tool-windows"></a>Araç pencereleri  
 Visual Studio aracı windows dosya tabanlı olmayan salt okunur genellikle windows ' dir. Bu konuda, dosyaları okuma-yazma modunda görüntülemek belge pencereleri farklı. **Araç**, **Çözüm Gezgini**, **özellikleri** penceresinde ve **Web tarayıcısı** aracı windows gösterilebilir.  
  
 Basit araç penceresi oluşturma konusunda bilgi edinmek için bkz: [araç penceresi ekleme](../extensibility/adding-a-tool-window.md).  
  
 Araç penceresi Visual Studio ile kaydetmek için bkz: [araç penceresi kaydetme](../extensibility/registering-a-tool-window.md).  
  
 Aracı windows Tek Örnekli varsayılan olarak, bu yalnızca bir araç penceresi örneği anlamı açık bir aynı anda olabilir. Tek örnek araç penceresi açıldıktan sonra IDE kapatılana kadar açık kalır. Tek örnek araç penceresini kapattığınızda, yalnızca görünürlüğü değiştirir. Aynı anda birden çok örneğini penceresi açılabilir şekilde, çok örnekli aracı windows oluşturabilirsiniz. Bkz: [çok örnekli araç penceresi oluşturma](../extensibility/creating-a-multi-instance-tool-window.md) daha fazla bilgi için.  
  
 Araç pencereleri olabilir *dinamik*, ilgili kullanıcı Arabirimi bağlamları geçerlidir her bunların görünür olduğunu anlamına gelir. Otomatik görünürlük kullanımını IDE içinde windows gösterip azaltabilir. Daha fazla bilgi için bkz: [dinamik bir aracı penceresini açma](../extensibility/opening-a-dynamic-tool-window.md).  
  
 Araç pencereleri yerleşik, kayan veya sekmeli belge çerçevede olabilir. Aracı pencere çerçevesi IDE tarafından sağlanır ve boyutu, konum, takma durumunu ve diğer kalıcı özellikleri denetlemek için kullanılır. Araç penceresi bölmesi içeriği görüntüler. Varsayılan boyut ve konum yalnızca araç penceresi ilk açıldığında uygulanır; Bundan sonra araç penceresi durumu kalıcıdır.  
  
 Aracı pencere bölmeleri WPF kullanıcı denetimi barındırmak ve araç çubuklarını destekler. Geçersiz kılabilirsiniz <xref:Microsoft.VisualStudio.Shell.WindowPane.Window%2A> denetimden tanıtıcısı döndürülecek özelliği.  
  
 Araç pencereleri birçok farklı özelliği ekleyebilirsiniz. Örneğin, bir araç çubuğu ekleyebilirsiniz: [araç çubuğu araç penceresi için ekleme](../extensibility/adding-a-toolbar-to-a-tool-window.md) veya bir kısayol menüsü: [araç penceresinde bir kısayol menüsü ekleme](../extensibility/adding-a-shortcut-menu-in-a-tool-window.md). Öğeleri araç penceresi içinde aramanıza olanak sağlayan bir arama denetimi ekleyebilirsiniz: [ekleme aramak için bir araç penceresi](../extensibility/adding-search-to-a-tool-window.md).  
  
 Araç penceresi olaylarına abone olabilirsiniz: [bir olaya abone](../extensibility/subscribing-to-an-event.md).  
  
## <a name="extending-existing-tool-windows"></a>Varolan araç pencereleri genişletme  
 Bilgi araç penceresi hakkında yeni bir ekleyebileceğiniz **seçenekleri** sayfası ve yeni bir ayar **özellikleri** sayfasında, yazma **görev listesi** ve **çıktı**  windows. Daha fazla bilgi için bkz: [özellikleri, görev listesi, çıkış ve seçenekleri Windows genişletme](../extensibility/extending-the-properties-task-list-output-and-options-windows.md) ve [özellikleri, görev listesi, çıkış ve seçenekleri Windows genişletme](../extensibility/extending-the-properties-task-list-output-and-options-windows.md).  
  
## <a name="modal-dialog-boxes"></a>Kalıcı iletişim kutuları  
 Visual Studio Uzantısı'nda onlardan türetme kalıcı iletişim kutuları oluşturmalısınız <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName>, bunları ve rest UI denetimi sağlar. Daha fazla bilgi için bkz. [Oluşturma ve yönetme kalıcı iletişim kutuları](../extensibility/creating-and-managing-modal-dialog-boxes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araç Penceresi İçeren Bir Uzantı Oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md)