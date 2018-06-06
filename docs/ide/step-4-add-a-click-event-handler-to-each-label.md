---
title: '4. adım: her etikete click olay işleyicisi ekleme'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 16bdbc7c-4129-411d-bace-f4a3e5375975
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f95a58c1e816c448a641a81282aaecf9d51a63ea
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748120"
---
# <a name="step-4-add-a-click-event-handler-to-each-label"></a>4. adım: her etikete click olay işleyicisi ekleme
Eşleştirme oyunu aşağıdaki gibi çalışır:

1.  Oyuncu gizli simge içeren karelerden birini seçtiğinde, program simge rengini siyaha dönüştürerek bu simgeyi oyuncuya gösterir.

2.  Oyuncu daha sonra başka bir gizli simge seçer.

3.  Simgeler eşleşirse görünür olarak kalırlar. Aksi takdirde iki simge de tekrar gizlenir.

 Bu şekilde çalışması için program almak için eklediğiniz bir <xref:System.Windows.Forms.Control.Click> seçilir etiketi rengini değiştirir olay işleyicisi.

## <a name="to-add-a-click-event-handler-to-each-label"></a>Her etikete click olay işleyicisi ekleme

1.  Formunda açmak **Windows Form Tasarımcısı**. İçinde **Çözüm Gezgini**, seçin *Form1.cs* veya *Form1.vb*. Menü çubuğunda seçin **Görünüm** > **Tasarımcısı**.

2.  İlk etiket denetimini belirleyip seçin. Ardından, basılı **Ctrl** her seçmek üzere diğer tüm etiketlere seçtiğiniz sırada anahtar. Her etiketin seçildiğinden emin olun.

3.  Seçin **olayları** araç çubuğu düğmesini **özellikleri** penceresini görüntülemek için **olayları** sayfasındaki **özellikleri** penceresi. Ekranı aşağı kaydırarak **tıklatın** olayı ve girin **label_Click** kutusunda aşağıdaki resimde gösterildiği gibi.

     ![Özellikler penceresini tıklatın gösteren olay](../ide/media/express_labelclick.png)
**özellikleri** gösteren penceresi **tıklatın** olay

4.  Seçin **Enter** anahtarı. IDE ekler bir `Click` adlı olay işleyicisi `label_Click()` koduna ve her bir form üzerinde etiketleri kanca oluşturur.

5.  Kodun geri kalanını aşağıdaki gibi doldurun:

     [!code-csharp[VbExpressTutorial4Step2_3_4#4](../ide/codesnippet/CSharp/step-4-add-a-click-event-handler-to-each-label_1.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#4](../ide/codesnippet/VisualBasic/step-4-add-a-click-event-handler-to-each-label_1.vb)]

    > [!NOTE]
    >  Kopyalama ve yapıştırma, `label_Click()` kodunu el ile girerek, varolan değiştirdiğinizden emin olun yerine kod bloğu `label_Click()` kodu. Aksi takdirde, yinelenen bir kod bloğu ile karşı karşıya kalırsınız.

    > [!NOTE]
    >  Tanı `object sender` aynı kullanılan olarak olay işleyicisinin üst [Eğitmen 2: zamanlı matematik testi oluşturma](../ide/tutorial-2-create-a-timed-math-quiz.md) Öğreticisi. Sayfaya çünkü olayları tek olay işleyicisi yöntemi için farklı bir etiket denetimini tıklatın, aynı yöntemi kullanıcının hangi etiket olsun seçmesi çağrılır. Olay işleyicisi yöntemi adı kullanması için hangi etiket seçildi, bilmek ister `sender` etiket denetimi tanımlamak için. Yalnızca genel bir nesneyi, ancak özellikle bir etiket denetimi olmadığından emin ve adını kullanır yönteminin ilk satırı programı bildirir `clickedLabel` etiketin özellikleri ve yöntemleri erişmek için.

     Bu yöntem ilk denetler olup olmadığını `clickedLabel` başarıyla dönüştürüldü (bir nesneden bir etiket denetimi cast). Başarısız bir değeri olup olmadığını `null` (C#) veya `Nothing` (Visual Basic) ve kodun geri kalanı yönteminde yürütmek istemiyorsanız. Ardından, etiketin kullanarak yöntemi seçilen etiketin metin rengi denetler **ForeColor** özelliği. Etiketin metin rengi siyah ise, simge zaten seçilmiş ve yöntem bitmiş demektir. (Ne olduğunu `return` deyimi yapar: yöntemini yürütmenin durdurmak için program söyler.) Aksi takdirde simge seçilmemiş demektir ve dolayısıyla program etiketin metin rengini siyah olarak değiştirir.

6.  Menü çubuğunda seçin **dosya** > **Tümünü Kaydet** ilerleme durumunuzu kaydetmek ve menü çubuğunda seçmeniz **hata ayıklama** > **Başlat Hata ayıklama** programınızı çalıştırmak için. Mavi arka planlı boş bir form görmeniz gerekir. Formdaki hücrelerden herhangi birini seçtiğinizde, simgelerden birinin görünür hale gelmesi gerekir. Formda farklı yerler seçmeye devam edin. Siz simgeleri seçtikçe görünmeleri gerekir.

## <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için

-   Öğretici bir sonraki adıma dönmek için bkz: [5. adım: etiket başvuruları ekleme](../ide/step-5-add-label-references.md).

-   Eğitmen önceki adıma dönmek için bkz: [3. adım: her etikete rasgele simge atama](../ide/step-3-assign-a-random-icon-to-each-label.md).
