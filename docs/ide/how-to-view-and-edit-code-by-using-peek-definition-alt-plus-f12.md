---
title: "Nasıl yapılır: kodu görüntüleme ve düzenleme (Alt + F12) Özet tanımı kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 10/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45f3dd20-902a-4047-8cca-9f18216123f4
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bf0dd4ab4a60dc7cfdfd351aee59c4942f75ef69
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-view-and-edit-code-by-using-peek-definition-altf12"></a>Nasıl yapılır: Özet Tanımı'nı Kullanarak Kodu Görüntüleme ve Düzenleme (Alt+F12)
Kullanabileceğiniz **Peek tanımı** görüntülemek ve kodu yazdığınız kodu çıktığınızda geçmeden düzenlemek için komutu. **Tanım Ara** ve **Tanıma Git** aynı bilgileri gösterir, ancak **Peek tanımı** açılır pencerede, gösterir ve **Tanıma Git** gösterir ayrı kod penceresinde kod. **Tanıma Git** tanımı kod penceresine geçiş yapmak, içerik (diğer bir deyişle, etkin kod penceresi, geçerli satır ve imleç konumu) neden olur. Kullanarak **Peek tanımı**, görüntüleyebilir ve tanımını düzenlemek ve özgün kod dosyasında yerinizi tutarken tanım dosyası içinde hareket etme.  
  
 Kullanabileceğiniz **Peek tanımı** C#, Visual Basic ve C++ kodu ile. Visual Basic'te **Peek tanımı** bağlantısını gösterir **Nesne Tarayıcısı** tanımı meta veriler (yerleşik olan Örneğin, .NET Framework türleri) yoksa sembolleri.  
  
## <a name="working-with-peek-definition"></a>Özet Tanım ile Çalışma  
  
#### <a name="to-open-a-peek-definition-window"></a>Bir Özet Tanım penceresi açmak için    
1.  Seçerek bir tanımı iletiye göz atabilirsiniz **Özet tanımı** keşfetmek istediğiniz bir üye için bağlam menüsünden. Seçeneği etkinleştirilirse, Visual Studio 2017 içinde 15.4 ve sonraki sürümleri, size ayrıca tuşlarına basarak fareyle tanımı iletiye göz atabilirsiniz **Ctrl** (veya başka bir değiştiricisi) ve üye adı'nı tıklatın. Veya klavyeden basın **Alt + F12**.  
  
     Bu gösterimde **Peek tanımı** adlı bir yöntem için pencere `Print()`:  
  
     ![Pencere peek](../ide/media/peekwindow.png "PeekWindow")  
  
     Aşağıda tanım penceresi görüntülenir `printer.Print("Hello World!")` özgün dosyasındaki satır. Pencerede, özgün dosyanızdaki kodlardan hiçbiri gizlenmez. İzleyen satırlarını `printer.Print("Hello World!")` altında tanımı penceresi görünür.  
  
2.  İmleci, kod tanımı penceresinde farklı konumlara taşıyabilirsiniz. Özgün kod penceresinde yine de taşıyabilirsiniz.  
  
3.  Dizeyi tanım penceresinden kopyalayıp özgün koda yapıştırabilirsiniz. Dizeyi tanım penceresinden sürükleyip özgün koda da bırakabilirsiniz (tanım penceresinden silinmeden).  
  
4.  Seçerek tanımı pencerenizi kapatabilir **Esc** anahtar veya **kapatmak** tanımı penceresi sekmesindeki düğmesi.  
  
#### <a name="to-open-a-peek-definition-window-from-within-a-peek-definition-window"></a>Bir Özet Tanım penceresinin içinden Özet Tanım penceresi açmak için    
-   Zaten varsa bir **Peek tanımı** penceresi açık, çağırabilir **Peek tanımı** yeniden bu pencereyi kodunda üzerinde. Başka bir tanım penceresi açılır. Tanım penceresi sekmesinin yanında, tanım pencereleri arasında gezinmek için kullanabileceğiniz bir dizi içerik haritası noktası görünür. Her bir noktadaki araç ipucu, noktanın temsil ettiği tanım dosyasının dosya adını ve yolunu gösterir.  
  
     ![Peek pencere gözlem penceresi içinde](../ide/media/peekwithinpeek.png "PeekWithinPeek")  
  
#### <a name="to-use-peek-definition-with-multiple-results"></a>Özet Tanım komutunu birden çok sonuçla kullanmak için    
-   Kullanırsanız **Peek tanımı** birden fazla tanımı (örneğin, kısmi sınıflar) kodu, bir sonuç listesi kod tanım görünümü sağında görünür. Listede istediğiniz sonucu seçerek tanımını görüntüleyebilirsiniz.  
  
     ![Birden çok sonuç gözlem penceresinden](../ide/media/peekmultiple.png "PeekMultiple")  
  
#### <a name="to-edit-inside-the-peek-definition-window"></a>Özet Tanım penceresinin içinde düzenlemek için    
-   İçinde düzenlemek başlattığınızda bir **Peek tanımı** penceresinde, otomatik olarak değişiklik yaptığınız dosya olarak kod düzenleyicisinde ayrı bir sekmesinde açar ve yaptığınız değişiklikleri yansıtır. Yapmak, Geri Al ve değişiklikleri kaydetmek devam edebilirsiniz **Peek tanımı** penceresi ve sekmesinde bu değişiklikleri yansıtacak şekilde sürdürür. Bile kapatırsanız **Peek tanımı** Değişikliklerinizi kaydetmeden penceresinde, yapabilir, Geri Al ve bırakabilirsiniz tam olarak kaldığınız yerden yukarı çekme sekmesinde, daha fazla değişiklikleri kaydetmek **Peek tanımı** penceresi.  
  
     ![Peek penceresi içinde düzenleme](../ide/media/peekedit.png "PeekEdit")  
  
#### <a name="to-change-options-for-peek-definition"></a>Peek tanımı seçeneklerini değiştirmek için  
1. Git **Araçları**, **seçenekleri**, **metin düzenleyici**, **genel**.  

2. Seçeneğini **tanımı gözlem görünümünde açmak**.  

3. Tıklatın **Tamam** kapatmak için **seçenekleri** iletişim kutusu.  

     ![Fare tıklatma gözlem tanımı seçeneği ayarlama](../ide/media/editor_options_peek_view.png)  

#### <a name="to-use-keyboard-shortcuts-for-peek-definition"></a>Özet Tanım klavye kısayollarını kullanmak için    
-   Bu klavye kısayollarını kullanabilirsiniz **Peek tanımı** penceresi:  
  
    |İşlevi|Klavye kısayolu|  
    |-------------------|:-----------------------:|  
    |Tanım penceresini açma|Alt+F12|  
    |Tanım penceresini kapatma|Esc|  
    |Tanım penceresini bir normal belge sekmesine yükseltme|Shift+Alt+Home|  
    |Tanım pencereleri arasında gezinme|Ctrl+Alt+- ve Ctrl+Alt+=|  
    |Birden fazla sonuç arasında gezinme|F8ve Shift+F8|  
    |Kod düzenleyicisi penceresi ile tanım penceresi arasında geçiş yapma|Shift+Esc|  
  
    > [!NOTE]
    >  Kodda düzenlemek için aynı klavye kısayollarını kullanabilirsiniz bir **Peek tanımı** yazarken penceresini kullanma başka bir yerde Visual Studio'da.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Kodda gezinme](../ide/navigating-code.md)  
[Tanım ve Özet tanımı gidin](../ide/go-to-and-peek-definition.md)  
[Üretkenlik ipuçları](../ide/productivity-tips-for-visual-studio.md)