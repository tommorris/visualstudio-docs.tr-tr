---
title: "Mac için Visual Studio genişletme | Microsoft Docs"
Description: "Mac'in özellikleri ve işlevselliği için Visual Studio uzantısı paketleri adlı modüllerle genişletilebilir. Bu kılavuzun ilk bölümü, bir basit bir belgeye tarih ve saat eklemek için Visual Studio'yu Mac uzantısı paketi oluşturur. Bu kılavuz ikinci bölümü uzantı paketini sistemi ile ilgili temel bilgileri ve çekirdek temelini Mac için Visual Studio API bazıları sunar"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.technology: vs-ide-sdk
ms.assetid: D5245AB0-8404-426B-B538-F49125E672B2
ms.openlocfilehash: a1ef2b6416ec26cfc77f66ebf4ac2629c17295fa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-visual-studio-for-mac"></a>Mac için Visual Studio genişletme

Mac için Visual Studio adlı modülleri kümesinden oluşur *uzantısı paketleri*. Uzantı paketleri ek dil veya yeni bir proje şablonu için destek gibi Mac için Visual Studio yeni işlevsellik tanıtmak için kullanabilirsiniz.

Uzantı paketleri oluşturmak *uzantısı* diğer uzantısı paketleri noktaları. Uzantı, bağlı bir menü veya IDE komutların listesini gibi genişletilebilir alanları yer tutucular noktalarıdır. Uzantı paketinin yeni menü öğesi veya yeni bir komut gibi bir uzantı olarak adlandırılan yapılandırılmış veri düğümünün kaydederek bir uzantı noktasından oluşturabilirsiniz. Her uzantı noktası uzantıları, belirli türde gibi kabul bir *komutu*, *paneli*, veya *FileTemplate*. Uzantı noktalarını içeren bir modül olarak adlandırılan bir *eklenti konak*diğer uzantısı paketleri tarafından Genişletilebilir gibi.

Mac için Visual Studio özelleştirmek için derlemeler bir uzantı paketini Mac için Visual Studio önceden varolan kitaplıklarında Konaklara eklenti bulunan uzantısı noktalarından tarafından Aşağıdaki diyagramda gösterildiği gibi oluşturabilirsiniz:

![Eklenti mimarisi](media/extending-visual-studio-mac-addin1.png)

Mac için Visual Studio'dan oluşturmak bir uzantı paketini sırayla Visual Studio'dan uzantı noktaları Mac IDE için önceden varolan yapı uzantıları olmalıdır. Uzantı paketinin bir eklenti konak tanımlı bir uzantı noktası kullanır, bu barındırıyor olarak sınıflandırılır bir _bağımlılık_ bu uzantısı paketinde.

Bu modüler tasarımı avantajdır Mac için Visual Studio genişletilebilirdir--özel uzantı paketlerle üzerine kurulabilir birçok uzantı noktaları vardır. Geçerli uzantısı paketleri örnekleri C# ve F #, hata ayıklayıcı araçları ve proje şablonları için destek içerir.

> [!NOTE]
> **Not**: eklenti Maker önce 1.2 oluşturulmuş bir eklenti Maker projesini varsa, projenizin adımlarda özetlendiği gibi geçiş yapmanız [burada](https://mhut.ch/addinmaker/1.2).

<!---The [Walkthrough](~/extending-visual-studio-mac-walkthrough.md) topic explains how to build an extension package that uses a *Command* to insert the date and time into an open text document.--->

Bu bölümde eklenti Maker tarafından oluşturulan farklı dosyaları bakar ve bir komut uzantısını verileri gerektirir.

## <a name="attribute-files"></a>Öznitelik dosyaları

Uzantı paketleri C# öznitelikleri kullanıcıların adı, sürüm, bağımlılıklar ve diğer bilgileri hakkındaki meta verileri depolar. Eklenti Maker, metatabanını `AddinInfo.cs` ve `AssemblyInfo.cs` depolamak ve bu bilgileri düzenlemek için. Uzantı paketleri benzersiz bir kimliği olmalıdır ve ad alanı belirtilen kendi *eklentisi özniteliği*:

```
[assembly:Addin (
   "DateInserter",
   Namespace = "DateInserter",
   Version = "1.0"
)]
```

Uzantı paketleri, bunlar takın uzantı noktaları kendi uzantısı paketlerde bağımlılıkları da bildirmeniz gerekir. Bu derleme zamanında otomatik olarak başvurulur.

Ayrıca, ek başvurular kullanılarak projesi için çözüm panelinde eklenti başvuru düğümü tarafından aşağıdaki resimde gösterildiği gibi eklenebilir:

![Tarih ekran Ekle](media/extending-visual-studio-mac-addin13.png)

Ayrıca karşılık gelen sahip oldukları `assembly:AddinDependency ` adresindeki eklenen öznitelikler derleme zamanı. Meta veri ve bağımlılık bildirimleri yerinde olduktan sonra uzantı paketinin temel yapı taşlarını üzerinde odaklanabilirsiniz.

## <a name="extensions-and-extension-points"></a>Uzantılar ve uzantı noktaları

Bir uzantı noktası veri yapısı (bir türü), tanımlayan bir yer tutucudur uzantı belirli uzantısı noktası tarafından belirtilen yapısına uygun veri açıklarken. Ne tür uzantısı'nın kendi bildiriminde kabul edebilir uzantısı noktalarını belirtin. Uzantıları tür adları veya uzantı yollar kullanılarak bildirilir. Bkz: [uzantısı noktası başvurusu](http://monoaddins.codeplex.com/wikipage?title=Extension%20Points&referringTitle=Description%20of%20Add-ins%20and%20Add-in%20Roots) için gereksinim duyduğunuz uzantı noktası oluşturma hakkında daha ayrıntılı bir açıklama.

Visual Studio geliştirme Mac hızlı ve modüler için uzantı/uzantısı noktası mimarisi tutar. 

<!--Since there are a large number of extension types, this article focuses on the ones used in the extension package that was built in the [Walkthrough](~/extending-visual-studio-mac-walkthrough.md).-->

### <a name="command-extensions"></a>Komut uzantıları

<!--[Walkthrough](~/extending-visual-studio-mac-walkthrough.md) uses a Command Extension - an extension that points to methods that are called every time it is executed. -->

Komut uzantıları yürütülür her zaman, çağrılan yöntemler noktası uzantıları yer almaktadır.

Komut uzantıları girişlere ekleyerek tanımlanmış `/MonoDevelop/Ide/Commands` uzantı noktası. Biz bizim uzantısı'nda tanımlanan `Manifest.addin.xml` aşağıdaki kod ile:

 ```
<Extension path="/MonoDevelop/Ide/Commands/Edit">
  <command id="DateInserter.DateInserterCommands.InsertDate"
            _label="Insert Date"
            _description="Insert the current date"
            defaulthandler="DateInserter.InsertDateHandler" />
</Extension>
```

Uzantı düğüm, bu durumda takarak uzantı noktası belirten bir yol özniteliği içerir `/MonoDevelop/Ide/Commands/Edit`. Ayrıca, komutu bir üst düğüme görür. Komut düğümü aşağıdaki özniteliklere sahiptir:

*   **Kimliği** -bu komut için tanımlayıcısını belirtir. Komut tanımlayıcıları Numaralandırma üye olarak bildirilmesi gerekir ve komutlar için CommandItems bağlanmak için kullanılır.
*   **_label** -menülerde gösterilecek metin.
*   **_description** -araç çubuğu düğmeleri için araç ipucu olarak gösterilecek metin.
*   **defaultHandler** -belirtir `CommandHandler` komutu çalıştırır sınıfı

<!--To invoke the command from the Edit Menu, the walkthrough creates a CommandItem extension that plugs into the `/MonoDevelop/Ide/MainMenu/Edit` extension point:-->

İçine takılan CommandItem uzantısı `/MonoDevelop/Ide/MainMenu/Edit` uzantı noktası aşağıdaki kod parçacığında gösterilmiştir:

```
<Extension path="/MonoDevelop/Ide/MainMenu/Edit">
  <commanditem id="DateInserter.DateInserterCommands.InsertDate" />
</Extension>
```

Bir CommandItem kendi ID özniteliği bir menüsüne belirtilen bir komut yerleştirir. Bu CommandItem genişletme `/MonoDevelop/Ide/MainMenu/Edit` komutunun etiket görünür hale getirir uzantı noktası **Düzen menüsü**. Unutmayın **kimliği** CommandItem komutu düğümünün kimliğine karşılık gelen `InsertDate`. CommandItem kaldırmak için olsaydı **tarih Ekle** seçeneği Düzen menüsünden görünmez.

### <a name="command-handlers"></a>Komut işleyicileri

`InsertDateHandler` Uzantısıdır `CommandHandler` sınıfı. İki yöntem geçersiz kılmaları `Update` ve `Run`. `Update` Yöntemi sorgulanan her bir komut menüde gösterilen veya anahtar bağlama yürütülür. Bilgisi nesnesi değiştirerek komutunu devre dışı bırakmak veya görünmez yapma, yapabilirsiniz ve dizi komutları doldurmak. Bu `Update` yöntemi devre dışı bırakır komutu etkin bir bulamazsa *belge* ile bir *TextEditor* metin eklemek için:

```
protected override void Update (CommandInfo info)
{
    info.Enabled = IdeApp.Workbench.ActiveDocument?.Editor != null;
}
```

Geçersiz kılmak yeterlidir `Update` etkinleştirme veya komutu gizleme için özel bir mantık olduğunda yöntemi. `Run` Yöntemi, bir kullanıcı bir kullanıcı Düzen menüsünden komutu seçtiğinde oluşan bu durumda, bir komut yürütür her yürütür. Bu yöntem tarih ve saati metin düzenleyicisinde şapka ekler:

```
protected override void Run ()
{
  var editor = IdeApp.Workbench.ActiveDocument.Editor;
  var date = DateTime.Now.ToString ();
  editor.InsertAtCaret (date);
}
```

Komut türü bir numaralandırma üyesine içinde olarak bildirin `DateInserterCommands`:

```
public enum DateInserterCommands
{
  InsertDate,
}
```

Bu komut ve CommandItem birbirine bağlar - CommandItem seçildiğinde CommandItem komutu çağıran **Düzen menüsü**.

## <a name="ide-apis"></a>IDE API'leri

<!--The extension package detailed in the [Walkthrough](~/extending-visual-studio-mac-walkthrough.md) deals with the Text Editor in Visual Studio for Mac, but this is only one of many possible areas for customization. -->

Geliştirme için kullanılabilir alanlar kapsamı hakkında daha fazla bilgi için bkz: [uzantısı ağaç başvurusu](http://monodevelop.com/Developers/Articles/Extension_Tree_Reference) ve [API genel bakış](http://monodevelop.com/Developers/Articles/API_Overview). Gelişmiş uzantı paketleri oluştururken de bkz [Geliştirici makaleleri](http://monodevelop.com/Developers/Articles). Özelleştirme için alanlar kısmı bir listesi aşağıda verilmiştir:

*   Klavye takımı
*   Anahtar bağlama şemaları
*   ilkeleri
*   Kod biçimlendiricileri
*   Proje dosya biçimleri
*   Tercihler paneller
*   Seçenekler paneller
*   Hata ayıklayıcı protokolleri
*   Görselleştiriciler hata ayıklayıcı
*   Çalışma alanı düzenleri
*   Çözüm paneli ağaç düğümleri
*   Kaynak Düzenleyicisi kenar boşlukları
*   Birim testi motorları
*   Kod oluşturucuları
*   Kod parçacıkları
*   Hedef Çerçeve
*   Hedef çalışma zamanı
*   VC arka uç
*   Yeniden Düzenle
*   Yürütme işleyicileri
*   söz dizimi vurgulama

## <a name="additional-information"></a>Ek Bilgiler

> [!NOTE]
Şu anda genişletilebilirlik senaryoları için Visual Studio Mac için iyileştirme çalışıyoruz Uzantıları oluşturma ve Ek Yardım veya bilgi gerekir ya da geribildirim sağlamak istediğiniz varsa, lütfen doldurmak [Mac yazma uzantısı için Visual Studio](https://aka.ms/vsmac-extensions-survey) formu.