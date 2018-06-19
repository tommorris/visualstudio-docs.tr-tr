---
title: Visual Studio Mac kılavuz için genişletme
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.technology: vs-ide-sdk
ms.assetid: 7D00512B-9688-4D8D-87A7-F04F207E3D02
ms.openlocfilehash: fdfbc5c10c3b49165960938f7f8832f61a37a805
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
ms.locfileid: "31625080"
---
# <a name="extending-visual-studio-for-mac-walkthrough"></a>Visual Studio Mac kılavuz için genişletme

Bu konu, yapı aracılığıyla size rehberlik eder [basit uzantısı paketi](https://github.com/mjh4/AddIns/tree/master/DateInserter). Uzantı paketinin geçerli tarih ve saat bir açık metin belgesine eklemek kullanıcının sağlayan Mac'ın Düzen menüsü için Visual Studio'da yeni bir komut oluşturur.

Bu örnek, eklenti Maker kullanır. Eklenti Maker yeni bir proje şablonu oluşturur ve bizim Özel uzantı paketi için gerekli dosyaları ile doldurur.

1.   Zaten açık değilse, Mac için Visual Studio başlatarak başlayın:

  ![Visual Studio için Mac ekran görüntüsü](media/extending-visual-studio-mac-addin3.png)

2.   Yükleme _eklenti Maker uzantısı paketi_ Uzantı Yöneticisi'ni kullanarak. Visual Studio menüsünden **uzantıları...** :

  ![Eklenti Yöneticisi sekmesi](media/extending-visual-studio-mac-addin4.png)

3.   Galeri sekmesini ve türü `Addin Maker` sağ üst arama çubuğunu içine. Eklenti geliştirme kategoriden eklentisi Maker seçin ve tıklatın <kbd>yükleme</kbd>. Hiçbir şey görünüyorsa, yenileme isabet ve yeniden arayın:

  ![Eklenti Yöneticisi](media/extending-visual-studio-mac-addin5.png)

4.   Eklentisi Maker yüklü, uzantı paketinin oluşturmaya başlayabilirsiniz. Yeni bir çözüm oluşturmaya başlayın.

5.  Gelen **yeni çözüm iletişim**, seçin **diğer > çeşitli > Genel > Xamarin Studio eklentisi > C#** şablonu ve aşağıdaki ekran üzerinde yeni bir çözüm adı `DateInserter`:

  ![Yeni bir çözüm oluşturma](media/extending-visual-studio-mac-addin7New.png)

6.   Visual Studio Mac için yeni bir çözüm dolduracaktır.

  ![Doldurulan çözümü](media/extending-visual-studio-mac-addin8.png)

7.   Şablon kodunda kaldırmak `Manifest.addin.xml` ve şununla değiştirin:

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
        <ExtensionModel>
            <Extension path = "/MonoDevelop/Ide/Commands/Edit">
                <Command id = "DateInserter.DateInserterCommands.InsertDate"
                    _label = "Insert Date"
                    defaultHandler = "DateInserter.InsertDateHandler" />
            </Extension>

            <Extension path = "/MonoDevelop/Ide/MainMenu/Edit">
                <CommandItem id="DateInserter.DateInserterCommands.InsertDate" />
            </Extension>
        </ExtensionModel>
    ```

8.   Şimdi tarih ve saat metin düzenleyicisine ekleme sonunda işleyecek dosyaları ayarlamanız gerekir. Proje düğümüne sağ tıklayın ve yeni bir dosya ekleyin. Seçin **genel > boş sınıfı** ve yeni dosya adı *InsertDateHandler*:

  ![Tarih işleyicisi Ekle](media/extending-visual-studio-mac-addin9.png)

9.   Şimdi şablon kodundan kaldırmak `InsertDateHandler.cs` ve aşağıdaki kod ile değiştirin:

    ```cs
    using MonoDevelop.Components.Commands;
    using MonoDevelop.Ide;
    using MonoDevelop.Ide.Gui;
    using System;

    namespace DateInserter
    {
        class InsertDateHandler : CommandHandler
        {
            protected override void Run()
            {

            }

            protected override void Update(CommandInfo info)
            {

            }
        }
    }
    ```

  Biz bu iki yer tutucu yöntemleri daha sonra genişletin.

10.   Sağ **DateInserter** proje ve select **Ekle > yeni dosya**. Seçin **genel > boş numaralandırma**ve ardından yeni dosya adı *DateInserterCommands*:

  ![DateInserterCommands](media/extending-visual-studio-mac-addin10.png)

11.   Ekleme `InsertDate` komut yeni bir numaralandırma olarak `DateInserterCommands.cs` dosyası:

    ``` cs
    using System;

    namespace DateInserter
    {
        public enum DateInserterCommands
        {
            InsertDate,
        }
    }
    ```

12.   Bu noktada, bir çalışma uzantısı paketi gerekir. Teslim çalışmanızı kaydederek ve uygulamayı çalıştıran test edebilirsiniz. IDE, yeni uzantı paketinin yüklü Mac için Visual Studio yeni bir örneğini başlatır. Gider **Düzen menüsü**, Mac için Visual Studio adlı yeni bir seçenek olduğunu görürsünüz **tarih Ekle**aşağıdaki ekran görüntüsüne gösterildiği gibi:

  ![Tarih komutu ekleme](media/extending-visual-studio-mac-addin11.png)

  Geçerli uygulama yalnızca yer tutucu yöntemleri taşıdığından tarih Ekle menüden seçerek herhangi bir etkisi olduğuna dikkat edin.

13.   Framework uzantısı paketinin yerinde ve tarih ekleme'nın temelini oluşturan kod yazmak için zaman olur. İlk olarak, olduğundan emin olun **Ekle tarih komutu** kullanıcının dosya değiştirerek açık bir metin olduğunda yalnızca etkin `Update` yönteminde `InsertDateHandler.cs` aşağıdaki kod ile:

    ```cs
    protected override void Update(CommandInfo info)
    {
        info.Enabled = IdeApp.Workbench.ActiveDocument?.Editor != null;
    }
    ```

14.   Komut güncelleştirme `Run` yöntemi tarih ve saati ile aşağıdaki kodu ekleyin:

    ``` cs
    protected override void Run () {
        var editor = IdeApp.Workbench.ActiveDocument.Editor;
        var date = DateTime.Now.ToString ();
        editor.InsertAtCaret (date);

    }
    ```

15.   Son olarak, test etmek için bizim uzantı paketini şimdi çalıştırın. Mac için Visual Studio yeni örneğini seçin **Düzenle > tarih Ekle**. Geçerli tarih ve saat aşağıdaki ekran görüntüsüne gösterildiği gibi bizim şapka eklenir:

  ![Tarih ekran Ekle](media/extending-visual-studio-mac-addin12.png)
