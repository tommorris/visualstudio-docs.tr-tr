---
title: Blend'de XAML hatalarını ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 29a37182-2a2c-47e4-a4a9-2d5412738fed
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: ebcf0508c5bc4d5788be1f7515604b5b4be228f1
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31477459"
---
# <a name="debug-xaml-in-blend"></a>Blend'de XAML hatalarını ayıklama
Araçları kullanabilirsiniz [!INCLUDE[blend_first](../debugger/includes/blend_first_md.md)] uygulamanızı XAML'de hata ayıklamak için. Proje oluşturma sırasında herhangi bir hata görüntülenir **sonuçları** paneli. Hata ile ilgili biçimlendirme bulmak için bir hata çift tıklayın. İş için daha fazla yer gerekiyorsa, gizleyebilirsiniz **sonuçları** F12 tuşuna basarak paneli.  
  
## <a name="syntax-errors"></a>Sözdizimi hataları  
 XAML veya arka plan kodu dosyalarının dilin biçimlendirme kuralları uygulamazsanız sözdizimi hataları oluşur. Hatanın açıklaması, nasıl düzeltileceğini anlamanıza yardımcı olabilir. Listenin ayrıca dosyasının adını ve hatanın oluştuğu satır numarasını belirtir. XAML hatalar listelenir **biçimlendirme** sekmesinde **sonuçları** paneli.  
  
> [!TIP]
>  XAML bir XML tabanlı işaretleme dili ve XML sözdizimi kurallarına uyar.  
  
 Bazı yaygın nedenler XAML sözdizimi hataları:  
  
-   Bir anahtar sözcük yanlış yazılmıştır veya büyük harf ayrımı yanlıştır.  
  
-   Öznitelikler veya metin dizesini tırnak işareti eksik.  
  
-   XAML öğesinde bir kapatma etiketi eksiktir.  
  
-   XAML öğesi, izin verilmeyen bir konumda bulunmaktadır.  
  
 Ortak XAML sözdizimi hakkında daha fazla bilgi için bkz: [temel XAML sözdizimi Kılavuzu](http://go.microsoft.com/fwlink/?LinkId=329942).  
  
 Ayrıca belirleyin ve çalışma zamanı hataları, derleme hataları ve basit arka plan kodu sözdizimi hataları çözün [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)]. Ancak, arka plan kod hataları belirlemek ve Visual Studio'da çözümlemek amacıyla daha kolay olabilir.  
  
### <a name="debugging-sample-xaml-code"></a>Örnek XAML kodda hata ayıklama  
 Aşağıdaki örnek hata ayıklama oturumunda basit bir XAML size yol gösterecek [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)].  
  
##### <a name="to-create-a-project"></a>Bir proje oluşturmak için  
  
1.  İçinde [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)], açık **dosya** menüsüne ve ardından **yeni proje**.  
  
     İçinde **yeni proje** iletişim kutusu, proje türleri listesi sol tarafında görüntülenir. Proje türü tıkladığınızda, kendisiyle ilişkili proje şablonları sağ tarafında görünür.  
  
2.  Proje türleri listesinde tıklatın **Windows Evrensel**.  
  
3.  Proje şablonları listesinde tıklatın **boş uygulama (Evrensel Windows)**.  
  
4.  İçinde **adı** metin kutusuna `DebuggingSample`.  
  
5.  İçinde **konumu** metin kutusunda, proje konumunu doğrulayın.  
  
6.  İçinde **dil** tıklatın **Visual C#** ve ardından **Tamam** projesi oluşturmak için.  
  
7.  Tasarım yüzeyine sağ tıklayın ve ardından **kaynağı görüntüle** geçmek için **bölünmüş** görünümü.  
  
8.  Tıklayarak aşağıdaki kodu kopyalayın **kopyalama** kodu sağ üst köşesindeki bağlantı.  
  
    ```  
    <Grid HorizontalAlignment="Left" Height="222" VerticalAlignment="Top>  
         <Button content="Button" x:Mame="Home" HorizontalAlignment="Left" VerticalAlignment="Top"/>  
         <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,38,0,0">  
         <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,75,0,0"/>  
         <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,112,0,0"/>  
         <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top Margin="0,149,0,0"/>  
    </Grid>  
  
    ```  
  
9. Varsayılan bulun **kılavuz**, açma ve kapatma arasında yer alan kodunu Yapıştır **kılavuz** etiketler. İşlemi tamamladığınızda, kodunuzu aşağıdaki gibi görünmelidir:  
  
    ```  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
         <Grid HorizontalAlignment="Left" Height="222" VerticalAlignment="Top>  
              <Button content="Button" x:Mame="Home" HorizontalAlignment="Left" VerticalAlignment="Top"/>  
              <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,38,0,0">  
              <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,75,0,0"/>  
              <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,112,0,0"/>  
              <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top Margin="0,149,0,0"/>  
         </Grid>  
    </Grid>  
  
    ```  
  
10. Projeyi derlemek için Ctrl + Shift + B tuşuna basın.  
  
 Proje oluşturulamıyor, size uyarı bir hata iletisi görüntülenir ve **sonuçları** hataları listeleme paneli uygulama alt kısmında görüntülenir.  
  
 ![Visual Studio için blend'de XAML hatalarını ayıklama](../debugger/media/blend_debugxaml_xaml.png "blend_debugXAML_XAML")  
  
### <a name="resolving-xaml-errors"></a>XAML hatalarını çözme  
 XAML hatalar algılandığında tasarım yüzeyine projenizi geçersiz biçimlendirme içeren bir uyarı görüntüler. Hataları giderin gibi hata listeyi **sonuçları** Masası güncelleştirilir. Tüm hataları çözdükten tasarım yüzeyine etkin ve uygulamanızı tasarım yüzeyine görüntülenir.  
  
##### <a name="to-resolve-the-xaml-errors"></a>XAML hatalarını gidermek için  
  
1.  Listedeki ilk hata çift tıklayın. Açıklama "değeri ' <' özniteliği geçerli değil." Hata çift tıkladığınızda işaretçinin kodda karşılık gelen konumu bulur. `<` Önceki `Button` geçerli olduğundan ve bir öznitelik değil hata iletisindeki önerilen olarak. Kod önceki satırında bakarsanız, kapanış tırnak özniteliğini işaretleri fark edeceksiniz `Top` eksik. Kapanış tırnak işaretleri yazın. Hata listesi bildirimi **sonuçları** panel yaptığınız değişiklikleri yansıtacak şekilde güncelleştirmeler.  
  
2.  Açıklama çift tıklatın "'0' geçersiz bir ad başlangıcında." `Margin="0,149,0,0"` düzgün biçimlendirilmemiş görünüyor. Ancak, dikkat edin, renk kodlama `Margin` diğer örneklerini eşleşmiyor `Margin` kod. Kapanış tırnak işaretleri önceki ad/değer çiftini eksik olduğundan (`VerticalAlignment="Top`), `Margin="` önceki öznitelik ve 0 değerinin bir parçası olarak bir ad/değer çifti başlangıcı salt okunur olduğundan okuyun. İçin kapanış tırnak işareti yazın `Top`. Hata listesinde **sonuçları** panel yaptığınız değişiklikleri yansıtacak şekilde güncelleştirmeler.  
  
3.  "XML etiketi 'Düğmesini' kapanış eşleşmiyor." kalan hatayı çift tıklatın İşaretçinin kapatma sırasında bulunduğu **kılavuz** etiketi (`</Grid>`), içinde hata olan öneren `Grid` nesne. Dikkat ikinci `Button` kapanış etiketi eksik. Kapatma ekledikten sonra `/`, **sonuçları** Masası listesi güncelleştirilir. Bu ilk hataları çözümlendi, iki ek hataları belirlenmiştir.  
  
4.  "'Content' üye tanınmıyor veya erişilebilir değil." çift tıklatın `c` İçinde `content` büyük harf olmalıdır. Bir büyük harf ile "c" küçük "c" değiştirin  
  
5.  Çift tıklatın "'Mame' bulunmuyor özelliği 'http://schemas.microsoft.com/winfx/2006/xaml' ad alanı." "Mame" "M" "N" olması gerekir "N" ile "M" değiştirin XAML ayrıştırılabilir, uygulama tasarım yüzeyine görünür.  
  
     ![Visual Studio için blend'de XAML hata ayıklama](../debugger/media/blend_debugartboard_xaml.png "blend_debugArtboard_XAML")  
  
     Projenizi derleme ve kalan hata olduğunu onaylamak için Ctrl + Shift + B tuşuna basın.  
  
## <a name="debugging-in-visual-studio"></a>Visual Studio'da Hata Ayıklama  
 Açabilirsiniz [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)] Visual Studio projelerinde daha kolayca uygulamanızı kodda hata ayıklama. Açmak için bir [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)] Visual Studio projesi,'nde projeye sağ **projeleri** panel ve ardından **Visual Studio'da Düzenle**. Visual Studio'da hata ayıklama oturumunuz tamamladıktan sonra tüm değişikliklerinizi kaydetmek ve daha sonra dönmek için Ctrl + Shift + S tuşlarına basın [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)]. Proje yeniden istenir. Tıklatın **Tümüne Evet** çalışmaya devam etmek için [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)].  
  
 Uygulamanızı hata ayıklama hakkında daha fazla bilgi için bkz: [Visual Studio'da hata ayıklama UWP uygulamaları](http://go.microsoft.com/fwlink/?LinkId=329944).  
  
## <a name="getting-help"></a>Yardım alma  
 Hata ayıklama için daha fazla yardıma ihtiyacınız varsa, [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)] uygulama, arayabilirsiniz [UWP uygulaması topluluk forumları](http://go.microsoft.com/fwlink/?LinkId=280308) gönderileri sorununuzu ilgili veya bir soru gönderin.