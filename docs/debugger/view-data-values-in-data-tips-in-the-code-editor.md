---
title: Görüntüleme veri değerleri DataTips Kod düzenleyicisinde | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], DataTips
- DataTips tool
ms.assetid: ffa7bd18-439b-4685-a9b3-c7884b5de41f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0c098e4b4ae94c5145a193e1903aa04a0eb757b4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="view-data-values-in-datatips-in-the-code-editor"></a>Kod düzenleyicisinde DataTips görünüm veri değerleri
DataTips hata ayıklama sırasında programınıza değişkenleri hakkında bilgi görüntülemek için kolay bir yol sağlamak. Kesme modunda yalnızca ve yalnızca yürütme geçerli kapsamdaki değişkenler DataTips çalışın.
  
### <a name="to-display-a-datatip"></a>Bir DataTip görüntülemek için  
  
1. Bir kesme noktası ayarlayın ve hata ayıklamayı Başlat (basın **F5**).

2. Hata ayıklayıcıda duraklatıldı yerlerde, fare işaretçisini geçerli kapsamdaki herhangi bir değişken üzerine getirin.
  
     Bir DataTip görünür.
  
3.  Fare işaretçisini kaldırdığınızda DataTip kaybolur. Böylece açık kalır DataTip sabitlemek için tıklatın **PIN kaynağına** simgesini veya bir değişkeni sağ tıklatın ardından **PIN kaynağına**.

    ![Bir veri ipucu sabitleme](../debugger/media/dbg-tips-data-tips-pinned.png "PinningDataTip")

    > [!NOTE]
    > Veri ipuçları, her zaman yürütme askıya alınır ve imleci değil getirildiğinde burada bağlamında değerlendirilir. Geçerli bağlamda olan bir değişken aynı ada sahip başka bir işlevi bir değişkende üzerine getirirseniz, diğer işlevinde değişkeninin değeri geçerli bağlamda değişkenin değeri olarak görüntülenir.
  
### <a name="to-unpin-a-datatip-and-make-it-float"></a>Bir DataTip kaldırın ve bunu yapmak için float  
  
-   Sabitlenmiş bir DataTip içinde tıklatın **telefondaki kaynağından** simgesi.  
  
     Sabitleme simgesine sabitlenmemiş konumunu değiştirir. DataTip artık herhangi bir açık windows kayar. Hata ayıklama oturumu sona erdiğinde kayan DataTip kapatır.  
  
### <a name="to-repin-a-floating-datatip"></a>Kayan DataTip repin için  
  
-   Bir DataTip içinde sabitleme simgesine tıklayın.  
  
     Sabitleme simgesine sabitlenmiş konumunu değiştirir. DataTip kaynak penceresi dışında ise, PIN simgesi devre dışıdır ve DataTip sabitlenir.  
  
### <a name="to-close-a-datatip"></a>Bir DataTip kapatmak için  
  
-   Fare işaretçisini DataTip getirin ve ardından **Kapat** simgesi.  
  
### <a name="to-close-all-datatips"></a>Tüm DataTips kapatmak için  
  
-   Üzerinde **hata ayıklama** menüsünde tıklatın **Temizle tüm DataTips**.  
  
### <a name="to-close-all-datatips-for-a-specific-file"></a>Belirli bir dosya için tüm DataTips kapatmak için  
  
-   Üzerinde **hata ayıklama** menüsünde tıklatın **Temizle tüm DataTips sabitlenmiş için** *dosya*.  
  
## <a name="expand-and-edit-information"></a>Genişletin ve bilgilerini Düzenle  
 DataTips bir dizi, bir yapı veya üyeleri görüntülemek için bir nesne genişletmek için kullanabilirsiniz. Bir DataTip değişkeninden değerini de düzenleyebilirsiniz.  
  
#### <a name="to-expand-a-variable-to-see-its-elements"></a>Öğeleri görmek için bir değişken genişletmek için  
  
-   Fare işaretçisini bir DataTip içinde yerleştirin **+** değişken adından önce gelen oturum.  
  
    Ağaç biçiminde öğeleri göstermek için değişkeni genişletir.

    ![Veri ipucunu görüntüleme](../debugger/media/dbg-tour-data-tips.gif "veri ipucunu görüntüleme")
  
    Değişkeni genişletildiğinde klavyenizde yukarı ve aşağı taşımak için ok tuşlarını kullanabilirsiniz. Alternatif olarak, fare kullanabilirsiniz.  
  
#### <a name="to-edit-the-value-of-a-variable-using-a-datatip"></a>Bir DataTip kullanarak bir değişken değerini düzenlemek için  
  
1.  Bir DataTip içinde değeri'ni tıklatın. Bu salt okunur değerlerini devre dışı bırakılır.  
  
2.  Yeni bir değer yazın ve ENTER tuşuna basın.  
  
## <a name="making-a-datatip-transparent"></a>Bir DataTip saydam hale getirme  
 DataTip kod görmek istiyorsanız, DataTip geçici olarak saydam hale getirebilirsiniz. Bu sabit veya değişken DataTips için geçerli değildir.  
  
#### <a name="to-make-a-datatip-transparent"></a>Bir DataTip saydam hale getirmek için  
  
-   Bir DataTip içinde CTRL tuşuna basın.  
  
     CTRL tuşunu basılı tutun sürece DataTip saydam kalır.  
  
## <a name="visualize-complex-data-types"></a>Karmaşık veri türlerini Görselleştirme  
 Büyüteç simgesini bir değişken adı bir veya daha fazla DataTip içinde yanında görünürse [görselleştiriciler](../debugger/create-custom-visualizers-of-data.md), gibi [dize görselleştiriciler](../debugger/string-visualizer-dialog-box.md), bu veri türündeki değişkenler için kullanılabilir. Görselleştirici daha anlamlı, genellikle grafik bir biçimde bilgileri görüntülemek için kullanabilirsiniz.
  
#### <a name="to-view-the-contents-of-a-variable-using-a-visualizer"></a>Görselleştirici kullanarak bir değişken içeriğini görüntülemek için  
  
-   Büyüteç simgesini ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Görselleştirici simgesi") veri türü için varsayılan Görselleştirici seçin.  
  
     -veya-  
  
     Veri türü için uygun görselleştiriciler listesinden seçmek için Görselleştirici yanındaki açılan oka tıklayın.  
  
     Görselleştirici bilgileri görüntüler.  
  
## <a name="add-information-to-a-watch-window"></a>Gözcü penceresi için bilgi Ekle  
 Liste görünümünde bir değişken izlemek devam etmek istiyorsanız değişkeni eklemek **izleme** bir DataTip penceresinden.  
  
#### <a name="to-add-a-variable-to-the-watch-window"></a>Gözcü penceresi için bir değişken eklemek için  
  
-   Bir DataTip sağ tıklayın ve ardından **Gözcü Ekle**.  
  
     Değişkeni eklenen **izleme** penceresi. Birden çok destekleyen bir sürümünü kullanıyorsanız, **izleme** windows, değişkeni eklenen **izleme 1.**  
  
## <a name="import-and-export-datatips"></a>İçeri ve dışarı aktarma DataTips  
 DataTips iş arkadaşı ile paylaşılabilir veya bir metin düzenleyicisi kullanarak düzenlenebilir bir XML dosyasına aktarabilirsiniz.  
  
#### <a name="to-export-datatips"></a>DataTips dışarı aktarmak için  
  
1.  Hata Ayıklama menüsünde **verme DataTips**.  
  
     **Verme DataTips** iletişim kutusu görüntülenir.  
  
2.  XML dosyasını, dosya için bir ad yazın istediğiniz konuma gitmek için standart dosya tekniklerini kullanın **dosya adı** kutusuna ve ardından **Tamam**.  
  
#### <a name="to-import-datatips"></a>DataTips içeri aktarmak için  
  
1.  Hata Ayıklama menüsünde **alma DataTips**.  
  
     **Alma DataTips** iletişim kutusu görüntülenir.  
  
2.  İletişim kutusunu açın ve tıklatın istediğiniz XML dosyasını bulmak için kullanın **Tamam**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)   
 [İzleme ve QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Özel Görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md)   