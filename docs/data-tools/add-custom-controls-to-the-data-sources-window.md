---
title: "Veri kaynakları penceresine özel denetimler ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.datasource.howtoaddcustomcontrol
helpviewer_keywords:
- Data Sources Window, adding controls
- controls [Visual Studio], adding to Data Sources Window
- DefaultBindingPropertyAttribute class, using
- LookupBindingPropertiesAttribute class, using
- ComplexBindingPropertiesAttribute class, using
- Data Sources Window, selecting controls
ms.assetid: 8c43e7d2-ba94-4d9b-96de-3aa971955afd
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: d1efd7051d9119c4d0e6643c1d42e78d9cdde7cf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="add-custom-controls-to-the-data-sources-window"></a>Veri kaynakları penceresine özel denetimler ekleme
Bir öğeden sürüklediğinizde **veri kaynakları** veri bağlama denetimi oluşturmak için tasarım yüzeyi penceresine, oluşturduğunuz denetim türünü seçebilirsiniz. Her öğenin penceresinde seçebileceğiniz denetimleri görüntüleyen bir açılır liste vardır. Her öğeyle ilişkili denetimleri kümesini öğesi veri türüne göre belirlenir. Oluşturmak istediğiniz denetimi listede görünmüyorsa, denetim listesine eklemek için bu konudaki yönergeleri izleyebilir.  
  
 Öğeleri oluşturmak için veri bağlama denetimleri seçme hakkında daha fazla bilgi için **veri kaynakları** penceresinde bkz [veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).  
  
> [!NOTE]
>  İletişim kutuları ve menü komutlarını gördüğünüz açıklanana Yardım'da etkin ayarlarınıza veya sürümünüze bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için **Araçları** menüsünde, select **içeri ve dışarı aktarma ayarları**. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
##  <a name="customizinglist"></a>Bir veri türü için bağlanabilirse denetimleri listesi özelleştirme  
 Denetimleri eklemek veya öğeler için kullanılabilir denetimler listesinden kaldırmak için **veri kaynakları** aşağıdaki adımları gerçekleştirin bir özel veri türüne sahip penceresi.  
  
#### <a name="to-select-the-controls-to-be-listed-for-a-data-type"></a>Bir veri türü için listelenecek denetimleri seçmek için  
  
1.  WPF Tasarımcısı'nı veya Windows Form Tasarımcısı açık olduğundan emin olun.  
  
2.  İçinde **veri kaynakları** penceresinde penceresine eklenen veri kaynağının parçası olan bir öğeyi tıklatın ve açılır menü öğesi için'ye tıklayın.  
  
3.  Aşağı açılan menüye tıklayın **Özelleştir**. Aşağıdaki iletişim kutularından birinin açar:  
  
    -   Windows Form Tasarımcısı açıksa **veri UI özelleştirme** sayfasında **seçenekleri** iletişim kutusu açılır.  
  
    -   WPF Tasarımcısı açıksa **denetim bağlamayı Özelleştir** iletişim kutusu açılır.  
  
4.  İletişim kutusunda veri türünden **veri türü** aşağı açılan liste.  
  
    -   Bir tablo veya nesne için denetimleri listesi özelleştirmek için seçin **[List]**.  
  
    -   Tablodaki bir sütun ya da bir nesnenin bir özelliğini denetimleri listesi özelleştirmek için temel alınan veri deposunda sütun veya özelliğin veri türünü seçin.  
  
    -   Kullanıcı tanımlı şekiller sahip veri nesneleri göstermek için denetimleri listesi özelleştirmek için seçin **[diğer]**. Örneğin, seçin **[diğer]** uygulamanızı belirli bir nesnenin birden fazla özellik verileri görüntüleyen özel bir denetim varsa.  
  
5.  İçinde **denetimleri ilişkili** kutusunda, seçili veri türü için kullanılabilir olmasını istediğiniz her bir denetimi seçin veya listeden kaldırmak istediğiniz herhangi bir denetim seçimini.  
  
    > [!NOTE]
    >  Seçmek istediğiniz denetimi görünmez, **denetimleri ilişkili** kutusu, denetim listesine eklemeniz gerekir. Daha fazla bilgi için bkz: [denetimlere listesini, ilişkili bir veri türü için ekleme denetimlerini](#addingcontrols).  
  
6.  **Tamam**'ı tıklatın.  
  
7.  İçinde **veri kaynakları** penceresinde, bir veri öğesi yalnızca bir veya daha fazla denetim ilişkili yazın ve ardından açılır menü öğesi için tıklatın.  
  
     Seçtiğiniz denetimleri **denetimleri ilişkili** kutusu artık görünür açılır menü öğesi için.  
  
##  <a name="addingcontrols"></a>Bir veri türü için ilişkili denetimler listesine denetimleri ekleme  
 Bir veri türüne sahip bir denetim ilişkilendirmek istediğiniz, ancak denetim görünmez **denetimleri ilişkili** kutusu, denetim listesine eklemeniz gerekir. Geçerli çözümde veya başvurulan bir derleme denetimi bulunmalıdır. Bu da kullanılabilir olmalıdır **araç kutusu**, ve denetimin veri bağlama davranışı belirten bir özniteliği vardır.  
  
#### <a name="to-add-controls-to-the-list-of-associated-controls"></a>Denetimleri ilişkili denetimler listesine eklemek için  
  
1.  İstenen denetimine ekleme **araç** sağ tıklanarak **araç** ve seçerek **öğeleri Seç**.  
  
     Denetimi aşağıdaki öznitelikler birine sahip olmalıdır.  
  
    |Öznitelik|Açıklama|  
    |---------------|-----------------|  
    |<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Gibi tek bir sütun (veya özelliği) verileri görüntüleyen basit denetimler Bu öznitelikte uygulayan bir <xref:System.Windows.Forms.TextBox>.|  
    |<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Bu öznitelik veri listeleri (veya tablo) görüntüleme denetimlerinde gibi uygulama bir <xref:System.Windows.Forms.DataGridView>.|  
    |<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Bu öznitelik veri ancak tek bir sütun veya özelliği sunmak gerek listeleri (veya tablo) görüntüleme denetimlerinde gibi uygulama bir <xref:System.Windows.Forms.ComboBox>.|  
  
2.  Windows Forms için üzerinde **seçenekleri** açık iletişim kutusunu **veri UI özelleştirme** sayfası. Veya, WPF için açık **denetim bağlamayı Özelleştir** iletişim kutusu. Daha fazla bilgi için bkz: [bir veri türü için liste, bağlanabilirse denetimleri özelleştirme](#customizinglist).  
  
3.  İçinde **denetimleri ilişkili** kutusunda için eklediğiniz denetim **araç** şimdi gösterilmelidir.  
  
    > [!NOTE]
    >  Geçerli çözümde veya başvurulan bir derleme bulunan denetimler yalnızca ilişkili denetimler listesine eklenebilir. (Denetimler de veri bağlama özniteliklerinden biri önceki tabloda uygulamanız gerekir.) Kullanılabilir olmayan bir özel denetim veri bağlamak için **veri kaynakları** penceresinde, denetimden sürükleyin **araç** tasarım yüzeyi ve ardından sürükleyin gelen bağlamak için öğeyi üzerine **veri Kaynakları** denetimi üzerine penceresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)