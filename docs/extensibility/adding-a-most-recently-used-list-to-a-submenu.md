---
title: Bir en kısa süre önce kullanılan bir alt listesine ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- MRU lists
- menus, creating MRU list
- most recently used
ms.assetid: 27d4bbcf-99b1-498f-8b66-40002e3db0f8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 67eb08feff5d8edd1251c8fcff09d8f148b51b96
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-most-recently-used-list-to-a-submenu"></a>Alt menü listesine kullanılan bir en kısa süre önce ekleme
Bu kılavuzda gösterim inşa edilmiştir [bir alt menüye ekleme](../extensibility/adding-a-submenu-to-a-menu.md)ve menüye dinamik bir listesi eklemeyi gösterir. Dinamik listenin en son kullanılan (MRU) listesini oluşturmak için temelini oluşturur.  
  
 Bir yer tutucu menüsündeki Dinamik menü listesini başlatır. Menü gösterilen her zaman, Visual Studio tümleşik geliştirme ortamı (IDE) VSPackage yer tutucu gösterilmesi gereken tüm komutlar için sorar. Dinamik bir listesi, herhangi bir yere menüde ortaya çıkabilir. Ancak, dinamik listeleri genellikle tutulur ve başlarına alt menüler üzerinde veya menüleri alta görüntülenir. Bu tasarım modelleri kullanarak, dinamik genişletin ve diğer komutları menüsünde konumunu etkilemeden sözleşme komutların listesini etkinleştirin. Bu kılavuzda, alt geri kalanından bir çizgiyle ayrılmış var olan bir alt kısımdaki dinamik MRU listesi görüntülenir.  
  
 Teknik olarak, dinamik bir listesi için bir araç çubuğu uygulanabilir. Ancak, kullanıcıyı değiştirmek için belirli adımlar götürür sürece bir araç çubuğu değişmeden kalmalıdır çünkü Biz bu kullanımı önerilmemektedir.  
  
 Bu kılavuz, birinin seçili her zaman kendi sırasını değiştirmek dört öğeleri MRU listesi oluşturur (Seçili öğe listesinin en üstüne taşır).  
  
 Menüler ve .vsct dosyaları hakkında daha fazla bilgi için bkz: [komutları, menüleri ve araç çubuklarını](../extensibility/internals/commands-menus-and-toolbars.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="creating-an-extension"></a>Bir uzantısı oluşturma  
  
-   Konusundaki yordamları izleyin [bir alt menüye ekleme](../extensibility/adding-a-submenu-to-a-menu.md) aşağıdaki yordamlarda değiştirilir alt oluşturmak için.  
  
 Bu kılavuzda yordamlar VSPackage adı olduğunu varsayar `TopLevelMenu`, kullanılan adı [Visual Studio menü çubuğunda bir menü ekleme](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md).  
  
## <a name="creating-a-dynamic-item-list-command"></a>Bir dinamik öğe listesi komutu oluşturma  
  
1.  Open TestCommandPackage.vsct.  
  
2.  İçinde `Symbols` bölümünde `GuidSymbol` guidTestCommandPackageCmdSet, adlı düğüm eklemek için simge `MRUListGroup` grup ve `cmdidMRUList` gibi komutu.  
  
    ```csharp  
    <IDSymbol name="MRUListGroup" value="0x1200"/>  
    <IDSymbol name="cmdidMRUList" value="0x0200"/>  
    ```  
  
3.  İçinde `Groups` bölümü, Grup girdilerinin sonra bildirilen grubunu ekleyin.  
  
    ```cpp  
    <Group guid="guidTestCommandPackageCmdSet" id="MRUListGroup"   
           priority="0x0100">  
        <Parent guid="guidTestCommandPackageCmdSet" id="SubMenu"/>  
    </Group>  
  
    ```  
  
4.  İçinde `Buttons` bölümünde, yeni bildirilen komut düğmesi girdilerinin sonra temsil etmek için bir düğüm ekleyin.  
  
    ```csharp  
    <Button guid="guidTestCommandPackageCmdSet" id="cmdidMRUList"  
        type="Button" priority="0x0100">  
        <Parent guid="guidTestCommandPackageCmdSet" id="MRUListGroup" />  
        <CommandFlag>DynamicItemStart</CommandFlag>  
        <Strings>  
            <CommandName>cmdidMRUList</CommandName>  
            <ButtonText>MRU Placeholder</ButtonText>  
                </Strings>  
    </Button>  
    ```  
  
     `DynamicItemStart` Bayrağı dinamik olarak oluşturulacak şekilde komutu sağlar.  
  
5.  Projeyi oluşturun ve yeni bir komut görüntüsünü test etmek için hata ayıklamayı Başlat.  
  
     Üzerinde **TestMenu** menüsünde Yeni alt tıklatın **alt menü**, yeni bir komut görüntülenecek **MRU yer tutucu**. Dinamik MRU komutların listesini bir sonraki yordamda uygulandıktan sonra bu komutu etiket alt açıldığında her zaman bu listeyi değiştirilecek.  
  
## <a name="filling-the-mru-list"></a>MRU listesini doldurma  
  
1.  TestCommandPackageGuids.cs içinde varolan komut kimliklerini sonra aşağıdaki satırları ekleyin `TestCommandPackageGuids` sınıf tanımının.  
  
    ```csharp  
    public const string guidTestCommandPackageCmdSet = "00000000-0000-0000-0000-00000000"; // get the GUID from the .vsct file  
    public const uint cmdidMRUList = 0x200;  
    ```  
  
2.  TestCommand.cs içinde aşağıdaki ekleme deyimini kullanarak.  
  
    ```csharp  
    using System.Collections;  
    ```  
  
3.  Aşağıdaki kodu TestCommand oluşturucuda son AddCommand çağrısından sonra ekleyin. `InitMRUMenu` Daha sonra tanımlanacak  
  
    ```csharp  
    this.InitMRUMenu(commandService);  
    ```  
  
4.  TestCommand sınıfında aşağıdaki kodu ekleyin. Bu kod MRU listede gösterilecek öğe temsil eden dizeleri listesini başlatır.  
  
    ```csharp  
    private int numMRUItems = 4;  
    private int baseMRUID = (int)TestCommandPackageGuids.cmdidMRUList;  
    private ArrayList mruList;  
  
    private void InitializeMRUList()  
    {  
        if (null == this.mruList)  
        {  
            this.mruList = new ArrayList();  
            if (null != this.mruList)  
            {  
                for (int i = 0; i < this.numMRUItems; i++)  
                {  
                    this.mruList.Add(string.Format(CultureInfo.CurrentCulture,  
                        "Item {0}", i + 1));  
                }  
            }  
        }  
    }  
    ```  
  
5.  Sonra `InitializeMRUList` yöntemi Ekle `InitMRUMenu` yöntemi. MRU Listesi menü komutlarını başlatır.  
  
    ```csharp  
    private void InitMRUMenu(OleMenuCommandService mcs)  
    {  
        InitializeMRUList();  
        for (int i = 0; i < this.numMRUItems; i++)  
        {  
            var cmdID = new CommandID(  
                new Guid(TestCommandPackageGuids.guidTestCommandPackageCmdSet), this.baseMRUID + i);  
            var mc = new OleMenuCommand(  
                new EventHandler(OnMRUExec), cmdID);  
            mc.BeforeQueryStatus += new EventHandler(OnMRUQueryStatus);  
            mcs.AddCommand(mc);  
        }  
    }  
    ```  
  
     MRU listesinde olası her öğe için bir menü komut nesnesi oluşturmanız gerekir. IDE çağrıları `OnMRUQueryStatus` kalmayana kadar daha fazla öğe MRU listesindeki her bir öğe için yöntem. Yönetilen kodda, yalnızca başka öğe yok olduğunu öğrenmek IDE için tüm olası öğeleri oluşturmak için öncelikle yoludur. İsterseniz, ek öğeleri olarak görünmez ilk kullanarak işaretleyebilirsiniz `mc.Visible = false;` menü komutu oluşturulduktan sonra. Bu öğeler ardından daha sonra kullanarak görünür hale getirilebilir `mc.Visible = true;` içinde `OnMRUQueryStatus` yöntemi.  
  
6.  Sonra `InitMRUMenu` yöntemi, aşağıdaki ekleyin `OnMRUQueryStatus` yöntemi. Her MRU öğesi için metin ayarlar işleyici budur.  
  
    ```csharp  
    private void OnMRUQueryStatus(object sender, EventArgs e)  
    {  
        OleMenuCommand menuCommand = sender as OleMenuCommand;  
        if (null != menuCommand)  
        {  
            int MRUItemIndex = menuCommand.CommandID.ID - this.baseMRUID;  
            if (MRUItemIndex >= 0 && MRUItemIndex < this.mruList.Count)  
            {  
                menuCommand.Text = this.mruList[MRUItemIndex] as string;  
            }  
        }  
    }  
    ```  
  
7.  Sonra `OnMRUQueryStatus` yöntemi, aşağıdaki ekleyin `OnMRUExec` yöntemi. MRU öğeyi seçmek için işleyici budur. Bu yöntem, seçili öğe listesinin en üstüne taşır ve ardından seçilen öğe bir ileti kutusu görüntüler.  
  
    ```csharp  
    private void OnMRUExec(object sender, EventArgs e)  
    {  
        var menuCommand = sender as OleMenuCommand;  
        if (null != menuCommand)  
        {  
            int MRUItemIndex = menuCommand.CommandID.ID - this.baseMRUID;  
            if (MRUItemIndex >= 0 && MRUItemIndex < this.mruList.Count)  
            {  
                string selection = this.mruList[MRUItemIndex] as string;  
                for (int i = MRUItemIndex; i > 0; i--)  
                {  
                    this.mruList[i] = this.mruList[i - 1];  
                }  
                this.mruList[0] = selection;  
                System.Windows.Forms.MessageBox.Show(  
                    string.Format(CultureInfo.CurrentCulture,  
                                  "Selected {0}", selection));  
            }  
        }  
    }  
  
    ```  
  
## <a name="testing-the-mru-list"></a>MRU Listesi test etme  
  
#### <a name="to-test-the-mru-menu-list"></a>MRU menü listesi sınamak için  
  
1.  Projeyi derleyin ve hata ayıklamayı Başlat  
  
2.  Üzerinde **TestMenu** menüsünde tıklatın **çağırma TestCommand**. Bunun yapılması komutu seçilmiş olduğunu belirten bir ileti kutusu görüntüler.  
  
    > [!NOTE]
    >  Bu adım, yüklemek ve doğru şekilde MRU listesini görüntülemek için VSPackage zorlamak için gereklidir. Bu adımı atlarsanız, MRU listesinde görüntülenmez.  
  
3.  Üzerinde **Test menü** menüsünde tıklatın **alt menü**. Dört öğeleri listesi, ayırıcı aşağıda alt sonunda görüntülenir. Tıkladığınızda **öğesi 3**, bir ileti kutusu görünür ve "Seçili öğesi 3" metin görüntüleme. (Dört öğeleri listesi görüntülenmiyorsa, önceki adımda'ndaki yönergeleri izlediğinizden emin olun.)  
  
4.  Alt yeniden açın. Dikkat **öğesi 3** listesinin başında sunulmuştur ve diğer öğeler bir konum aşağı gönderildikten. Tıklatın **öğesi 3** yeniden ve metin komutu etiketi ile birlikte yeni konuma doğru taşındı gösteren ileti kutusu hala "3 Seçili öğesi" görüntüler dikkat edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dinamik Olarak Menü Öğeleri Ekleme](../extensibility/dynamically-adding-menu-items.md)