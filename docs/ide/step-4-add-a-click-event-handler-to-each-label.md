---
title: "4. adım: her etikete Click olay işleyicisi ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16bdbc7c-4129-411d-bace-f4a3e5375975
caps.latest.revision: "20"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: ca218a20f46bf1233602287b1ad374921f85428a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="step-4-add-a-click-event-handler-to-each-label"></a>4. Adım: Her Etikete Click Olay İşleyicisi Ekleme
Eşleştirme oyunu aşağıdaki gibi çalışır:  
  
1.  Oyuncu gizli simge içeren karelerden birini seçtiğinde, program simge rengini siyaha dönüştürerek bu simgeyi oyuncuya gösterir.  
  
2.  Oyuncu daha sonra başka bir gizli simge seçer.  
  
3.  Simgeler eşleşirse görünür olarak kalırlar. Aksi takdirde iki simge de tekrar gizlenir.  
  
 Programınızın bu şekilde çalışmasını sağlamak için, seçilen etiketin rengini değiştiren bir Tıklama olayı işleyicisi eklersiniz.  
  
### <a name="to-add-a-click-event-handler-to-each-label"></a>Her etikete bir Tıklama olayı işleyicisi eklemek için  
  
1.  Formu Windows Form Tasarımcısı'nda açın. Çözüm Gezgini'nde Form1.cs veya Form1.vb öğesini seçin. Menü çubuğunda seçin **Görünüm**, **Tasarımcısı**.  
  
2.  İlk etiket denetimini belirleyip seçin. Ardından CTRL tuşunu basılı tutarken diğer etiketleri tek tek belirleyip seçin. Her etiketin seçildiğinden emin olun.  
  
3.  Seçin **olayları** araç çubuğu düğmesini **özellikleri** penceresini görüntülemek için **olayları** sayfasındaki **özellikleri** penceresi. Ekranı aşağı kaydırarak **tıklatın** olayı ve girin **label_Click** kutusunda aşağıdaki resimde gösterildiği gibi.  
  
     ![Özellikler penceresini tıklatın gösteren olay](../ide/media/express_labelclick.png "Express_labelClick")  
Tıklama olayını gösteren Özellikler penceresi  
  
4.  ENTER tuşunu seçin. IDE adlı bir Click olay işleyicisi ekler `label_Click()` koduna ve her bir form üzerinde etiketleri kanca oluşturur.  
  
5.  Kodun geri kalanını aşağıdaki gibi doldurun:  
  
     [!code-csharp[VbExpressTutorial4Step2_3_4#4](../ide/codesnippet/CSharp/step-4-add-a-click-event-handler-to-each-label_1.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#4](../ide/codesnippet/VisualBasic/step-4-add-a-click-event-handler-to-each-label_1.vb)]  
  
    > [!NOTE]
    >  Kopyalama ve yapıştırma, `label_Click()` kodunu el ile girerek, varolan değiştirdiğinizden emin olun yerine kod bloğu `label_Click()` kodu. Aksi takdirde, yinelenen bir kod bloğu ile karşı karşıya kalırsınız.  
  
    > [!NOTE]
    >  Tanı `object sender` aynı kullanılan olarak olay işleyicisinin üst [Eğitmen 2: bir zaman aşımına matematik test oluşturma](../ide/tutorial-2-create-a-timed-math-quiz.md) Öğreticisi. Tek bir olay işleyicisi yöntemine farklı etiket denetimi Tıklama olayı tutturduğunuzdan, kullanıcının seçtiği etiket hangisi olursa olsun aynı yöntem çağrılır. Olay işleyicisi yöntemi adı kullanması için hangi etiket seçildi, bilmek ister **gönderen** etiket denetimi tanımlamak için. Yalnızca genel bir nesneyi, ancak özellikle bir etiket denetimi olmadığından emin ve adını kullanır yönteminin ilk satırı programı bildirir **clickedLabel** etiketin özellikleri ve yöntemleri erişmek için.  
  
     Bu yöntem ilk denetler olup olmadığını **clickedLabel** başarıyla dönüştürüldü (bir nesneden bir etiket denetimi cast). Başarısız bir değeri olup olmadığını `null` (C#) veya `Nothing` (Visual Basic) ve kodun geri kalanı yönteminde yürütmek istemiyorsanız. Ardından, etiketin kullanarak yöntemi seçilen etiketin metin rengi denetler **ForeColor** özelliği. Etiketin metin rengi siyah ise, simge zaten seçilmiş ve yöntem bitmiş demektir. (Ne olduğunu `return` deyimi yapar: yöntemini yürütmenin durdurmak için program söyler.) Aksi takdirde simge seçilmemiş demektir ve dolayısıyla program etiketin metin rengini siyah olarak değiştirir.  
  
6.  Menü çubuğunda seçin **dosya**, **Tümünü Kaydet** ilerleme durumunuzu kaydetmek ve menü çubuğunda seçmeniz **hata ayıklama**, **hata ayıklamayı Başlat** çalıştırmak için programınızı. Mavi arka planlı boş bir form görmeniz gerekir. Formdaki hücrelerden herhangi birini seçtiğinizde, simgelerden birinin görünür hale gelmesi gerekir. Formda farklı yerler seçmeye devam edin. Siz simgeleri seçtikçe görünmeleri gerekir.  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [5. adım: etiket başvuruları ekleme](../ide/step-5-add-label-references.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [3. adım: her etikete rasgele simge atama](../ide/step-3-assign-a-random-icon-to-each-label.md).