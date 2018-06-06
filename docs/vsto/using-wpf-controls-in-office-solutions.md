---
title: Office çözümlerinde WPF denetimlerini kullanma
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WPF [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 87305902c80d9848df63d2c8bd9f431fd93a5508
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767601"
---
# <a name="use-wpf-controls-in-office-solutions"></a>Office çözümlerinde WPF denetimlerini kullanma
  Visual Studio'da Office geliştirme araçlarını kullanarak oluşturduğunuz çözümleri doğrudan Windows Forms denetimleri ile çalışmak için tasarlanmış olsa da, çözümlerinde WPF denetimleri de kullanabilirsiniz. Windows Presentation Foundation (WPF) Windows Forms için kullanıcı arabirimleri tasarlama için alternatiftir. WPF Genişletilebilir uygulama biçimlendirme dili (XAML) adlı bir işaretleme dili UI, ortam ve belgeler ekleme için yeni teknikler sağlamak için kullanır. Daha fazla bilgi için bkz: [Visual Studio 2015'te WPF'ye giriş](/dotnet/framework/wpf/getting-started/introduction-to-wpf-in-vs).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Office çözümünü Windows Forms denetimlerinde barındırabilir herhangi bir kullanıcı Arabirimi öğe WPF denetimleri de barındırabilir. Bunlar aşağıdaki öğeleri içerir:  
  
-   Belgeleri ve belge düzeyi özelleştirmelerinde çalışma.  
  
-   Belge düzeyi özelleştirmelerinde Eylemler bölmeleri.  
  
-   VSTO eklentileri özel görev bölmeleri.  
  
-   VSTO eklentileri için Outlook form bölgeleri.  
  
## <a name="add-wpf-controls-to-office-projects-at-design-time"></a>Office projeleri için tasarım zamanında WPF denetimleri ekleyin  
 Office çözümlerinde UI öğelerine doğrudan WPF denetimleri ekleyemezsiniz. Bunun yerine, ekleme bir **kullanıcı denetimi (WPF)** öğesi projenize ve WPF denetimleri için tasarım yüzeyi olarak kullanın. Daha sonra WPF kullanıcı denetimi UI öğesi projenize ekleyin.  
  
### <a name="to-add-wpf-controls-to-an-actions-pane-custom-task-pane-or-form-region"></a>Eylemler bölmesinde, özel görev bölmesini veya form bölgesi WPF denetimleri eklemek için  
  
1.  Özel görev bölmesi, Eylemler bölmesinde ya da bir form bölgesi eklemek istediğiniz bir projeyi açın.  
  
2.  Ekleme bir **kullanıcı denetimi (WPF)** projenize öğesi.  
  
3.  Gelen **araç**, WPF kullanıcı denetimi tasarım yüzeyine WPF denetimleri ekleyin.  
  
     WPF kullanıcı denetimi Tasarımcısı açıkken, varsayılan olarak, **araç** sadece WPF denetimleri içerir.  
  
4.  Projeyi oluşturun.  
  
5.  Eylemler bölmesi, form bölgesi veya özel görev bölmesi projenize ekleyin:  
  
    -   Form bölgeleri için ekleyin bir **Outlook Form bölgesi** proje öğesi. Daha fazla bilgi için bkz: [nasıl yapılır: bir Outlook eklenti projesine form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
    -   Eylemler bölmeleri için ekleyin bir **Eylemler bölmesi denetimi** veya **kullanıcı denetimi** proje öğesi. Daha fazla bilgi için bkz: [nasıl yapılır: Word belgelerine Eylemler bölmesi ekleme veya Excel çalışma kitapları](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md) ve [nasıl yapılır: Word belgelerine Eylemler bölmesi ekleme veya Excel çalışma kitapları](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md).  
  
    -   Özel görev bölmeleri için ekleyin bir **kullanıcı denetimi** proje öğesi. Daha fazla bilgi için bkz: [nasıl yapılır: uygulamaya özel görev bölmesi ekleme](../vsto/how-to-add-a-custom-task-pane-to-an-application.md).  
  
6.  Gelen *ProjectName* **WPF kullanıcı denetimi** sekmesinde **araç**, Eylemler bölmesinde, form bölgesi veya özel görev bölmesini tasarımcıya WPF kullanıcı denetimi sürükleyin.  
  
     Visual Studio otomatik olarak oluşturur bir <xref:System.Windows.Forms.Integration.ElementHost> UI öğesi üzerinde WPF kullanıcı denetimi barındıran nesne.  
  
7.  Projeyi yeniden oluşturun.  
  
#### <a name="to-add-wpf-controls-to-a-document-or-worksheet-in-a-document-level-project"></a>Bir belge veya belge düzeyi projesindeki çalışma sayfasına WPF denetimleri eklemek için  
  
1.  Word veya Excel için belge düzeyi projesini açın.  
  
2.  Ekleme bir **kullanıcı denetimi (WPF)** projenize öğesi.  
  
3.  Gelen **araç**, WPF kullanıcı denetimi tasarım yüzeyine WPF denetimleri ekleyin.  
  
4.  Projeyi oluşturun.  
  
5.  Ekleme bir **kullanıcı denetimi** projeye öğe (diğer bir deyişle, bir Windows Forms kullanıcı denetimi).  
  
6.  Windows Forms kullanıcı denetimi Tasarımcısı'nı açın.  
  
7.  Gelen *ProjectName* **WPF kullanıcı denetimi** sekmesinde **araç**, WPF kullanıcı denetimi tasarımcıya sürükleyin.  
  
     Visual Studio otomatik olarak oluşturur bir <xref:System.Windows.Forms.Integration.ElementHost> Windows Forms kullanıcı denetimi WPF kullanıcı denetimi barındıran nesne.  
  
8.  Windows Forms kullanıcı denetimi belge veya çalışma kitabını programlı olarak ekleyen kod yazın. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
    > [!NOTE]  
    >  Belge veya çalışma Tasarımcısı'nda Windows Forms kullanıcı denetimi sürükleyin olamaz.  
  
9. Projeyi yeniden oluşturun.  
  
## <a name="host-wpf-controls-by-using-the-elementhost-class"></a>ElementHost sınıfı kullanarak ana bilgisayar WPF denetimleri  
 Visual Studio yardımcı özellikleri Office çözümlerinde Windows Forms denetimleri kullanın, ancak benzer özellikleri WPF denetimleri için sağlamaz sağlar. Örneğin, Windows Forms denetimleri belgelere ve çalışma kitaplarına tasarım zamanında denetimlerden sürükleyerek ekleyebileceğiniz **araç**, veya yardımcı yöntemler kullanarak çalışma zamanında. Ancak, bu araçları WPF denetimleri için kullanılabilir değildir.  
  
 WPF denetimlerini kullanma <xref:System.Windows.Forms.Integration.ElementHost> sınıfı bir Windows Forms denetimi ya da formu ve WPF denetimleri arasındaki tümleştirme katmanı olarak. Çözümünüze tasarım zamanında WPF denetimleri eklediğinizde, Visual Studio'nun otomatik olarak oluşturduğu bir <xref:System.Windows.Forms.Integration.ElementHost> nesnesi.  
  
## <a name="wpf-resources"></a>WPF kaynakları  
 Daha fazla mimari hakkında bilgi ve Windows Forms denetimleri ve formlar üzerinde WPF denetimleri barındırma için tasarım konuları için aşağıdaki konulara bakın:  
  
-   [Windows Forms ve WPF birlikte çalışabilirlik girdi mimarisi](/dotnet/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture)  
  
-   [Windows Forms ve WPF özellik eşlemesi](/dotnet/framework/wpf/advanced/windows-forms-and-wpf-property-mapping)  
  
-   [WPF ve Windows Forms birlikte çalışma](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)  
  
-   [Windows Forms denetimleri ve eşdeğer WPF denetimleri](/dotnet/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls)  
  
 Windows Forms denetimleri ve Visual Studio formlarında tasarım zamanında WPF denetimleri ekleme hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [İzlenecek yol: yeni bir WPF içeriği Windows formlarında tasarım zamanında oluşturma](/dotnet/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time)  
  
-   [İzlenecek yol: Tasarım zamanında WPF içeriği Windows Forms'ta düzenleme](/dotnet/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time)  
  
-   [İzlenecek yol: Stil WPF içeriği](/dotnet/framework/winforms/advanced/walkthrough-styling-wpf-content)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Windows Forms denetimlerindeki Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)   
 [Özel görev bölmeleri](../vsto/custom-task-panes.md)   
 [Outlook form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [Nasıl yapılır: Word belgelerine Eylemler bölmesi ekleme veya Excel çalışma kitapları](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Nasıl yapılır: Word belgelerine Eylemler bölmesi ekleme veya Excel çalışma kitapları](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Nasıl yapılır: uygulamaya özel görev bölmesi ekleme](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [Nasıl yapılır: bir Outlook eklenti projesine form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)  
  
  