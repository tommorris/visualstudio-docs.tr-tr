---
title: Grafik kanal aşamaları | Microsoft Docs
ms.custom: ''
ms.date: 02/09/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.pipeline
ms.assetid: 2bf5c12e-2a00-401c-8163-4e373d08ad3f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c708320442c32158ef193ccf7f08669882135d82
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31481307"
---
# <a name="graphics-pipeline-stages"></a>Grafik Ardışık Düzen Aşamaları
Grafik ardışık düzen Aşamaları penceresi, tek tek çizim çağrısı her Direct3D grafik potansiyel satış aşamasına göre nasıl dönüştürülür anlamanıza yardımcı olur.  
  
 Bu ardışık düzen Aşamaları penceresi.  
  
 ![3B bir nesneyi ardışık düzen aşamaları gider.](media/gfx_diag_demo_pipeline_stages_orientation.png)
  
## <a name="understanding-the-graphics-pipeline-stages-window"></a>Grafik ardışık düzen Aşamaları penceresi anlama  
 Ardışık Düzen Aşamaları penceresi her grafik ardışık düzen aşaması sonucunu her çizim çağrısı için ayrı ayrı visualizes. Normalde, bir işleme sorun başlatıldığı söyleyin zorlaşır ortasında ardışık düzen aşamaları sonuçlarını gizlenir. Her aşamanın ayrı olarak görselleştirme ardışık düzen Aşamaları penceresi sorun başladığı görmeyi kolaylaştırır — Örneğin, kolayca köşe gölgelendirici aşama beklenmedik biçimde bir nesne off-screen çizilecek sebep olduğunda görebilirsiniz.  
  
 Sorunun oluştuğu aşama tanımladıktan sonra verileri nasıl yorumlanacağını veya dönüştürülmüş incelemek için bir grafik Çözümleyicisi araçları kullanabilirsiniz. Ardışık Düzen aşamaları görünen işleme genellikle ilgili yanlış köşe biçimi tanımlayıcıları, buggy gölgelendirici programları veya yanlış yapılandırılmış durumda sorunlardır.  
  
### <a name="links-to-related-graphics-objects"></a>İlişkili grafik nesnelerine giden bağlantıları  
 Bazen ek bağlam neden grafik ardışık düzen ile belirli bir şekilde bir çizim çağrı etkileşim belirlemek için gereklidir. Bu ek bağlam bulmayı kolaylaştırmak için grafik ardışık düzeninde neler nesnelere ek bağlam sağlayan bir veya daha fazla grafik ardışık düzen Aşamaları penceresi bağlantıları ilgili.  
  
-   Direct3D 12'de bu nesne, genellikle komut listesi verilmiştir.  
  
-   Direct3D 11'de bu genellikle bir grafik cihaz bağlamı nesnesidir.  
  
 Bu bağlantılar grafik ardışık düzen aşamaları pencerenin sol üst köşesinde bulunan geçerli grafik olay imza bir parçasıdır. Herhangi bir nesne hakkında ek ayrıntılar incelemek için bu bağlantıları izleyin.  
  
### <a name="viewing-and-debugging-shader-code"></a>Görüntüleme ve gölgelendirici kodda hata ayıklama  
 İnceleyin ve bunların ilgili aşamaları altındaki ardışık düzen Aşamaları penceresinde denetimlerini kullanarak köşe hull, etki alanı, geometri ve piksel gölgelendiriciler kodda hata ayıklama.  
  
#### <a name="to-view-a-shaders-source-code"></a>Gölgelendirici'nın kaynak kodunu görüntülemek için  
  
-   İçinde **grafik ardışık düzen aşamaları** penceresinde gölgelendirici karşılık gelen gölgelendirici aşama bulun incelemek istediğiniz. Ardından, Önizleme görünümü gölgelendirici aşama başlık bağlantıyı — Örneğin, bağlantıyı izleyerek **köşe gölgelendirici obj:30** köşe gölgelendirici kaynak kodunu görüntülemek için.  
  
    > [!TIP]
    >  Nesne numarası **obj:30**, bu gölgelendirici nesne tablo ve piksel Geçmişi penceresini olduğu gibi böyle grafik Çözümleyicisi arabirimi boyunca tanımlar.  
  
#### <a name="to-debug-a-shader"></a>Gölgelendirici hata ayıklamak için  
  
-   İçinde **grafik ardışık düzen aşamaları** penceresinde gölgelendirici karşılık gelen gölgelendirici aşama bulun hata ayıklamak istediğiniz. Ardından, Önizleme görünümü seçin **hata ayıklamayı Başlat**. Bu giriş noktasını gölgelendirici ilk çağırma karşılık gelen aşamasına HLSL hata ayıklayıcısı varsayılanlara içine — diğer bir deyişle, ilk piksel, köşe veya bu çizim çağrı sırasında gölgelendirici tarafından işlenen ilkel. Bu gölgelendirici belirli piksel veya köşe için çağrılarını üzerinden erişilebilir **grafik piksel geçmişi**.  
  
### <a name="the-pipeline-stages"></a>Ardışık Düzen aşamaları  
 Ardışık Düzen Aşamaları penceresi yalnızca çizim araması sırasında etkin ardışık düzen aşamaları visualizes. Grafik ardışık her aşama önceki aşamaya girişten dönüştürür ve sonucu sonraki aşamaya geçirir. İlk aşamada — giriş Assembler — dizin ve köşe veri uygulamanızdan; giriş olarak alır çok son aşaması — çıktı birleşme — birleştiren yeni piksel framebuffer geçerli içeriğini birlikte çizilir veya hedef Ekranınızda gördüğünüz son görüntü oluşturmak için çıktı olarak işlemek.  
  
> [!NOTE]
>  İşlem gölgelendiriciler desteklenmiyor **grafik ardışık düzen aşamaları** penceresi.  
  
 **Giriş derleyici**  
 Giriş Assembler uygulamanız tarafından belirtilen dizin ve köşe verileri okur ve grafik donanım derler.  
  
 Ardışık Düzen Aşamaları penceresinde giriş derleyici çıktı Tel Çerçeve model olarak görselleştirilen. Sonuç daha yakından bakmak için seçin **giriş Assembler** içinde **grafik ardışık düzen aşamaları** birleştirilmiş köşeleri tam 3D modeli Düzenleyicisi'ni kullanarak görüntülemek için pencere.  
  
> [!NOTE]
>  Varsa `POSITION` anlamsal giriş derleyici çıktısında mevcut değil ve hiçbir şey görüntülenir **giriş Assembler** aşaması.  
  
 **Köşe gölgelendirici**  
 Köşe gölgelendirici aşama genellikle kaplama ve ışık dönüştürme gibi işlemleri gerçekleştirme köşeleri işler. Köşe gölgelendiriciler üretmek bunlar alır köşeleri aynı sayıda giriş olarak.  
  
 Ardışık Düzen Aşamaları penceresinde köşe gölgelendirici çıktısı bir Tel Çerçeve ızgara görüntüsü olarak görselleştirilen. Sonuç daha yakından bakmak için seçin **köşe gölgelendirici** içinde **grafik ardışık düzen aşamaları** işlenen köşeleri görüntü Düzenleyicisi'nde görüntülemek için windows.  
  
> [!NOTE]
>  Varsa `POSITION` veya `SV_POSITION` semantiği köşe gölgelendirici çıktısında mevcut değildir ve hiçbir şey görüntülenir **köşe gölgelendirici** aşaması.  
  
 **Hull gölgelendirici** (Direct3D 11 ve Direct3D yalnızca 12)  
 Hull gölgelendirici süreci işlemleri satır, üçgen veya dört gibi düşük düzey yüzeyini tanımlayan noktası denetler. Çıkış olarak daha yüksek sıralı geometri düzeltme eki ve sabit işlevi Mozaik döşeme aşamaya geçirilen düzeltme eki sabitleri üretir.  
  
 Ardışık Düzen Aşamaları penceresinde hull gölgelendirici aşama görselleştirilen değil.  
  
 **Tessellator aşama** (Direct3D 11 ve Direct3D yalnızca 12)  
 Hull gölgelendirici çıktı tarafından temsil edilen etki alanı preprocesses sabit işlevi (programlanabilir olmayan) bir donanım birim tessellator aşamasıdır. Çıkış olarak örnekleme düzeni etki alanının ve daha küçük temelleri kümesi oluşturur — noktaları, satırlar, üçgenler — bu örnekleri bağlanın.  
  
 Ardışık Düzen Aşamaları penceresinde tessellator aşama görselleştirilen değil.  
  
 **Etki alanı gölgelendirici** (Direct3D 11 ve Direct3D yalnızca 12)  
 Etki alanı gölgelendirici aşama birlikte Mozaik döşeme Etkenler Mozaik döşeme Sahne Alanı'ndan daha yüksek sıralı geometri düzeltme ekleri Hull gölgelendirici gelen işler. Etkenler olabilir Mozaik döşeme tessellator giriş faktörü dahil yanı sıra Etkenler çıktı. Çıkış olarak tessellator Etkenler göre çıkış düzeltme eki noktasında köşe konumunu hesaplar.  
  
 Etki alanı gölgelendirici aşama ardışık düzen Aşamaları penceresinde görünür değil.  
  
 **Geometri gölgelendirici**  
 Tüm temelleri geometri gölgelendirici aşama işler — noktaları, çizgiler veya üçgenler — kenarıyla bitişik temelleri için isteğe bağlı köşe verileri birlikte. Köşe gölgelendiriciler aksine geometri gölgelendiriciler daha oluşturabilir veya olarak aldıkları daha az temelleri girdi.  
  
 Ardışık Düzen Aşamaları penceresinde geometri gölgelendirici çıktısı bir Tel Çerçeve ızgara görüntüsü olarak görselleştirilen. Sonuç daha yakından bakmak için seçin **geometri gölgelendirici** içinde **grafik ardışık düzen aşamaları** işlenen temelleri görüntü Düzenleyicisi'nde görüntülemek için pencere.  
  
 **Akış çıkışı aşaması**  
 Akış çıkışı aşama tarama önce dönüştürülmüş temelleri kesecek ve belleğe yazmayı; Buradan verileri önceki grafik ardışık düzen aşamaları giriş olarak recirculated veya CPU tarafından okunur.  
  
 Akış çıkışı aşama ardışık düzen Aşamaları penceresinde görünür değil.  
  
 **Tarayıcısını aşaması**  
 Tarayıcısını aşama vektör temelleri dönüştüren bir sabit işlevi (programlanabilir olmayan) donanım birimdir — noktaları, satırlar, üçgenler — tarama satırı dönüştürme gerçekleştirerek ızgara görüntüsü. Tarama sırasında köşeleri homojen küçük alanı dönüştürülen ve kırpılır. Çıktı olarak piksel gölgelendiriciler eşlenen ve köşe başına öznitelikleri arasında basit Ara değerli ve piksel gölgelendirici için hazır duruma.  
  
 Ardışık Düzen Aşamaları penceresinde tarayıcısını aşama görselleştirilen değil.  
  
 **Piksel gölgelendirici**  
 Piksel başına oluşturmak için piksel gölgelendirici aşama işlemleri rasterleştirilmiş temelleri Ara değerli köşe veri birlikte renk ve derinliği gibi değerler.  
  
 Ardışık Düzen Aşamaları penceresinde piksel gölgelendirici çıktısı bir tam renkli ızgara görüntüsü olarak görselleştirilen. Sonuç daha yakından bakmak için seçin **piksel gölgelendirici** içinde **grafik ardışık düzen aşamaları** işlenen temelleri görüntü Düzenleyicisi'nde görüntülemek için pencere.  
  
 **Çıktı birleşme**  
 Yeni oluşturulan piksel bunların karşılık gelen arabelleklerinin varolan içeriğini birlikte etkisini çıkış birleşme aşama birleştirir — rengi, derinliği ve şablon — bu arabellekleri yeni değerleri üretmek için.  
  
 Ardışık Düzen Aşamaları penceresinde çıktı birleşme çıkış tam renkli ızgara görüntüsü olarak görselleştirilen. Sonuçlar daha yakından bakmak için seçin **çıkış birleşme** içinde **grafik ardışık düzen aşamaları** birleştirilmiş framebuffer görüntülemek için pencere.  
  
### <a name="vertex-and-geometry-shader-preview"></a>Köşe ve geometri gölgelendirici Önizleme  
 Köşe veya geometri gölgelendirici aşamasında seçtiğinizde **ardışık düzen aşamaları** penceresinde görüntüleyebilirsiniz için girişleri ve çıkışları gölgelendirici öğesinden panelinde.  Burada, bunlar giriş assembler aşamasına göre birleştirilen sonra gölgelendiriciler sağlanan köşeleri listesi ayrıntılarını bulabilirsiniz.  

 ![Köşe gölgelendirici aşama giriş arabelleği Görüntüleyicisi](media/gfx_diag_vertex_shader_inbuffers.png)  
  
 Köşe gölgelendirici aşama sonucu görüntülemek için tam boyutlu, rasterleştirilmiş Tel Çerçeve sonra kafes, görüntülemek için köşe gölgelendirici aşama küçük resmini seçin, edilmiş tarafından köşe gölgelendirici dönüştürüldüğünde.  
  
 ![Köşe gölgelendirici aşama sonuç Önizleme](media/gfx_diag_vertex_shader_preview.png)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Köşe gölgeleme nedeniyle nesnelerin eksikliği](walkthrough-missing-objects-due-to-vertex-shading.md)   
 [İzlenecek Yol: Gölgeleme Nedeniyle Çıkan Oluşturma Hatalarını Ayıklama](walkthrough-debugging-rendering-errors-due-to-shading.md)