---
title: "Nasıl yapılır: uygulamaya özel görev bölmesi ekleme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- task panes [Office development in Visual Studio], adding to application
- custom task panes [Office development in Visual Studio], adding to application
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9e4e5d03dd08e4a7e8631db65c74b843720d037d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-custom-task-pane-to-an-application"></a>Nasıl Yapılır: Uygulamaya Özel Görev Bölmesi Ekleme
  VSTO eklentisini kullanarak bir özel görev bölmesi uygulamaları için yukarıda listelenen ekleyebilirsiniz. Daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="adding-a-custom-task-pane-to-an-application"></a>Uygulamaya özel görev bölmesi ekleme  
  
#### <a name="to-add-a-custom-task-pane-to-an-application"></a>Uygulamaya özel görev bölmesi ekleme  
  
1.  Bir VSTO eklenti projesi yukarıda listelenen uygulamalardan birinin oluşturun veya açın. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Üzerinde **proje** menüsünde tıklatın **kullanıcı denetimi Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, yeni kullanıcı denetimi adını değiştirmek **MyUserControl**ve ardından **Ekle**.  
  
     Kullanıcı denetimi Tasarımcısı'nda açılır.  
  
4.  Bir veya daha fazla Windows Forms denetimleri ekleme **araç** kullanıcı denetimi için.  
  
5.  Açık **ThisAddIn.cs** veya **ThisAddIn.vb** kod dosyası.  
  
6.  Aşağıdaki kodu ekleyin `ThisAddIn` sınıfı. Bu kod örneklerini bildirir `MyUserControl` ve <xref:Microsoft.Office.Tools.CustomTaskPane> üyeleri olarak `ThisAddIn` sınıfı.  
  
     [!code-vb[Trin_TaskPaneBasic#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#1)]
     [!code-csharp[Trin_TaskPaneBasic#1](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#1)]  
  
7.  Aşağıdaki kodu ekleyin `ThisAddIn_Startup` olay işleyicisi. Bu kod yeni bir oluşturur <xref:Microsoft.Office.Tools.CustomTaskPane> ekleyerek `MyUserControl` nesnesine `CustomTaskPanes` koleksiyonu. Kod ayrıca görev bölmesini görüntüler.  
  
     [!code-vb[Trin_TaskPaneBasic#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#2)]
     [!code-csharp[Trin_TaskPaneBasic#2](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#2)]  
  
    > [!NOTE]  
    >  Bu kod, özel görev bölmesini uygulamadaki etkin pencereyi ilişkilendirir. Bazı uygulamalar, görev bölmesinde diğer belgelerin veya öğelerin uygulamadaki ile görünmesini sağlamak için bu kodu değiştirmek isteyebilirsiniz. Daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Özel görev bölmeleri](../vsto/custom-task-panes.md)   
 [İzlenecek Yol: Uygulamayı Özel Görev Bölmesinden Otomatikleştirme](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)  
  
  