---
title: Office projelerinde erişilebilirlik
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, accessibility
- shortcut keys [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], shortcut keys
- accessibility [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 34a1ea090e85168b5fd0bf2e55c22d0a38ff331f
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="accessibility-in-office-projects"></a>Office projelerinde erişilebilirlik
  Microsoft Visual Studio ve Microsoft Office standart erişilebilirlik gereksinimlerini karşılayan özel çözümler oluşturmanıza olanak sağlayan birçok erişilebilirlik özelliği içerir. Microsoft Erişilebilirlik Web sayfasındaki yönergeleri yayımlar. Ayrıntılar için bkz [Erişilebilirlik Web sitesi](http://go.microsoft.com/fwlink/?LinkID=37113).  

 Çoğu durumda, Visual Studio'da Office projeleri çözümlerinizi erişilebilir hale getirmek için ayarlayabileceğiniz erişilebilirlik standartlarına veya açığa çıkarır özelliklerini karşılar. Ancak, sınırlı erişilebilirliği olan bazı özellikleri vardır.  

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  

## <a name="accessibility-at-design-time"></a>Tasarım zamanında erişilebilirlik  

### <a name="use-shortcut-keys-in-document-level-projects"></a>Belge düzeyi projelerine kısayol tuşlarını kullanın  
 Microsoft Office Word belgesine veya Microsoft Office Excel çalışma kitabı Visual Studio'da açık olduğunda, bir seferde yalnızca bir uygulama kısayol tuşu komutlarını alır. Varsayılan olarak, Visual Studio tüm kısayol tuşu komutlarını alır, ancak Word veya Excel belge seçerek odağa sahip olduğunda bunları almak yapabilirsiniz **dinamik klavye düzeni** üzerinde **klavye ayarları** sayfası **seçenekleri** iletişim kutusu. Daha fazla bilgi için bkz: [Microsoft Office Word Klavyesi, Microsoft Office Klavyesi ayarları, Seçenekler iletişim kutusu](../vsto/microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md) ve [Microsoft Office Excel Klavyesi, Microsoft Office Klavyesi ayarları, Seçenekler iletişim kutusu](../vsto/microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md).  

### <a name="display-shortcut-keys-for-the-ribbon-in-document-level-projects"></a>Belge düzeyi projelerine Şerit için kısayol tuşları görüntüleme  
 Word belgesine veya bir Excel çalışma kitabı Visual Studio'da açıkken basın olamaz **Alt** sekmeleri ve Şerit denetimleri için kısayol tuşlarını görmek için anahtar. Belge veya çalışma kitabı tasarımcıda açıkken kısayol tuşlarını görmek için aşağıdaki adımları gerçekleştirin.  

#### <a name="to-view-shortcut-keys-for-ribbon-tabs-and-controls-in-the-designer"></a>Tasarımcıda Şerit sekmeler ve denetimler için kısayol tuşlarını görüntülemek için  

1.  Visual Studio'da üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.  

2.  Genişletme **Office Araçları** düğümü ve select **Microsoft Office Excel Klavyesi** veya **Microsoft Office Word Klavyesi**uygun şekilde.  

3.  Seçin **dinamik klavye düzeni**.  

     Visual Studio değişikliğin etkili olması için yeniden başlatmanız gerektiğini bildiren bir ileti görüntülenir.  

4.  **Tamam**'ı tıklatın.  

5.  Visual Studio'yu yeniden başlatın ve projenizi yeniden açın.  

6.  Projeniz için belge veya çalışma kitabı Tasarımcısı'nı açın.  

7.  Tuşuna **F6** Şerit için kısayol tuşlarını görüntülemek için.  

## <a name="accessibility-at-runtime"></a>Çalışma zamanında erişilebilirlik  

### <a name="windows-forms-controls-on-office-documents"></a>Office belgelerindeki Windows Forms denetimleri  
 Windows Forms denetimleri ekran okuyucular gibi erişilebilirlik Yardımcıları denetimi hakkında bilgi sağlamak için erişilebilirlik özelliklerini kullanır. Belge düzeyi özelleştirmelerinde bir Office belgesine denetimleri olduğunda bu erişilebilirlik özelliklerinden yararlanabilir. Daha fazla bilgi için bkz: [bir Windows formundaki denetimler için erişilebilirlik bilgilerini](/dotnet/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form).  

 Ancak, Windows Forms denetimleri bir Excel çalışma kitabı veya Word belgesi barındırıldığında çalışma zamanında bazı erişilebilirlik sınırlamaları vardır:  

-   Bir denetimden başka bir sekmesinde olamaz.  

-   Belgenin yakınlaştırma ayarını % 100'den değiştirdiğinizde bir belgede denetimleri devre dışı bırakılır.  

 Belgelerindeki Windows Forms denetimleri sınırlamaları hakkında daha fazla bilgi için bkz: [Windows Forms sınırlamaları denetimleri Office belgeleri](../vsto/limitations-of-windows-forms-controls-on-office-documents.md).  

### <a name="actions-panes-and-custom-task-panes"></a>Eylemler bölmeleri ve özel görev bölmeleri  
 Eylemler bölmesi veya özel görev bölmesi odağa sahip olduğunda, bir Windows Forms uygulaması denetimlere erişir aynı şekilde erişimi kontrol eder. İmleci Eylemler bölmesi ve belge arasında taşımak için basabilirsiniz **F6**.  

 Eylemler bölmeleri ve özel görev bölmeleri hakkında daha fazla bilgi için bkz: [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md) ve [özel görev bölmeleri](../vsto/custom-task-panes.md).  

### <a name="display-modes"></a>Görüntü modları  
 Visual Studio görüntü modları ilgili aşağıdaki sınırlamalara sahiptir:  

-   Belgenin yakınlaştırma ayarını % 100'den değiştirdiğinizde bir Word belgesi veya Excel çalışma sayfasındaki denetimleri devre dışı bırakılır.  

-   **Yeni proje** iletişim kutusu denetimleri düzgün görüntülenemeyebilir kullanıcı bilgisayarın erişilebilirlik seçenekleri değişirse **Yüksek Karşıtlık kullan**.  

 Bu sınırlamaların üstesinden gelmek için Büyüteç'i kullanabilirsiniz. Büyüteç'i bir ekran büyütülmüş bir bölümünü görüntüler ayrı bir pencerede Windows görüntü aracıdır.  

## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri geliştirmek](../vsto/developing-office-solutions.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Engelli kişiler için erişilebilirlik](/visualstudio/ide/reference/accessibility-for-people-with-disabilities)   
 [Visual Studio'nun erişilebilirlik özellikleri](/visualstudio/ide/reference/accessibility-features-of-visual-studio)  
