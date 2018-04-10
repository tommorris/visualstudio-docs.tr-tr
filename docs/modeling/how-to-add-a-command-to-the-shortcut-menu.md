---
title: 'Nasıl yapılır: bir komut için kısayol menüsü ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language Tools, walkthroughs
- walkthroughs [Domain-Specific Language Tools]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 4f65964e1d7fd4221746d8ec17a498cf9ee3a354
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="how-to-add-a-command-to-the-shortcut-menu"></a>Nasıl yapılır: Kısayol Menüsüne Komut Ekleme
Kullanıcılarınızın, DSL belirli görevleri gerçekleştirebilmeleri için menü komutlarını, etki alanına özgü dil (DSL) ekleyebilirsiniz. Kullanıcıların Diyagramı sağ tıklattığınızda komutları (kısayol) bağlam menüsünde görüntülenir. Yalnızca belirli durumlarda menüsünde görünen komut tanımlayabilirsiniz. Yalnızca kullanıcı öğesi veya öğeleri belirli durumlarda belirli türlerdeki tıklattığında Örneğin, komut görünür duruma getirebilirsiniz.  
  
 Özet olarak, adımları DslPackage projesinde şu şekilde gerçekleştirilir:  
  
1.  [Commands.vsct komutunda bildirme](#VSCT)  
  
2.  [Package.tt, paketin sürüm numarasını güncelleştirmek](#version). Commands.vsct değiştirdiğinizde Bunu yapmak zorunda  
  
3.  [CommandSet sınıfında yöntemleri yazma](#CommandSet) komutu görünür hale getirmek için ve yapmak için komutun istediğiniz tanımlamak için.  
  
 Örnekler için bkz: [Görselleştirme ve modelleme SDK Web sitesi](http://go.microsoft.com/fwlink/?LinkID=185579).  
  
> [!NOTE]
>  CommandSet.cs yöntemleri geçersiz kılarak, kesme, yapıştırma, Tümünü Seç ve yazdırma gibi bazı mevcut komutları davranışını değişiklik yapabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: standart menü komutu değiştirme](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).  
  
## <a name="defining-a-command-using-mef"></a>MEF kullanarak bir komut tanımlama  
 Yönetilen uzantısı çerçevesi (MEF) diyagramı menüsünde menü komutları tanımlamak için alternatif bir yöntem sağlar. Birincil amacı, sizin tarafınızdan veya diğer taraflar tarafından genişletilmesi DSL sağlamaktır. Kullanıcılar yalnızca DSL yüklemeyi seçebilirsiniz veya DSL ve uzantılarını yükleyebilirsiniz. Ancak, MEF MEF DSL üzerinde etkinleştirmek için ilk iş sonra kısayol menü komutları tanımlama işlemlerini azaltır.  
  
 Yöntemi bu konudaki kullanın:  
  
1.  Menü komutları sağ kısayol menüsünün dışında menülerde tanımlamak istersiniz.  
  
2.  Komutları belirli gruplandırmaları menüde tanımlamak istersiniz.  
  
3.  Başkalarının kendi komutlarla DSL genişletmek etkinleştirmek istediğiniz değil.  
  
4.  Yalnızca bir komuta tanımlamak istersiniz.  
  
 Aksi takdirde, komutları tanımlamak için MEF yöntemi kullanmayı düşünün. Daha fazla bilgi için bkz: [MEF kullanarak, DSL genişletme](../modeling/extend-your-dsl-by-using-mef.md).  
  
##  <a name="VSCT"></a> Commands.Vsct komutunda bildirme  
 Menü komutları DslPackage\Commands.vsct bildirilir. Bu tanımları menü öğelerinin ve menülerde nerede göründüklerinden etiketlerini belirtin.  
  
 Düzenleme, dosya Commands.vsct, tanımları dizininde bulunan birkaç .h dosyaları alır *Visual Studio SDK yükleme yolu*\VisualStudioIntegration\Common\Inc. Ayrıca, DSL tanımından oluşturulan GeneratedVsct.vsct içerir.  
  
 .Vsct dosyaları hakkında daha fazla bilgi için bkz: [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
#### <a name="to-add-the-command"></a>Komut eklemek için  
  
1.  İçinde **Çözüm Gezgini**altında **DslPackage** proje, Commands.vsct açın.  
  
2.  İçinde `Commands` öğesi, bir veya daha fazla düğme ve bir grubu tanımlayın. A *düğmesini* menüsünde bir öğedir. A *grup* menü bölümündedir. Bu öğeleri tanımlamak için aşağıdaki öğeleri ekleyin:  
  
    ```  
    <!-- Define a group - a section in the menu -->  
    <Groups>  
      <Group guid="guidCustomMenuCmdSet" id="grpidMyMenuGroup" priority="0x0100">  
        <!-- These symbols are defined in GeneratedVSCT.vsct -->  
        <Parent guid="guidCmdSet" id="menuidContext" />  
      </Group>  
    </Groups>  
    <!-- Define a button - a menu item - inside the Group -->  
    <Buttons>  
      <Button guid="guidCustomMenuCmdSet" id="cmdidMyContextMenuCommand"  
        priority="0x0100" type="Button">  
        <Parent guid="guidCustomMenuCmdSet" id="grpidMyMenuGroup"/>  
        <!-- If you do not want to place the command in your own Group,   
             use Parent guid="guidCmdSet" id="grpidContextMain".  
             These symbols are defined in GeneratedVSCT.vsct -->  
        <CommandFlag>DynamicVisibility</CommandFlag>  
        <Strings>  
          <ButtonText>My Context Menu Command</ButtonText>  
        </Strings>  
      </Button>  
    </Buttons>  
    ```  
  
    > [!NOTE]
    >  Her düğme veya gruba bir GUID ve bir tamsayı kimlik tarafından tanımlanan Aynı GUID ile çeşitli gruplar ve düğmeleri oluşturabilirsiniz. Ancak, farklı kimlikleri olması gerekir. GUID adları ve kimliği adları gerçek GUID ve sayısal kimlikleri için çevrilir `<Symbols>` düğümü.  
  
3.  Komutu için görünürlüğü kısıtlama ekleyebilirsiniz, böylece yalnızca etki alanına özgü dil bağlamında yüklenir. Daha fazla bilgi için bkz: [VisibilityConstraints öğesi](../extensibility/visibilityconstraints-element.md).  
  
     Bunu yapmak için aşağıdaki öğeleri ekleyin `CommandTable` öğeden sonra `Commands` öğesi.  
  
    ```  
    <VisibilityConstraints>  
      <!-- Ensures the command is only loaded for this DSL -->  
      <VisibilityItem guid="guidCustomMenuCmdSet" id="cmdidMyContextMenuCommand"  
        context="guidEditor"/>  
    </VisibilityConstraints>  
    ```  
  
4.  GUID ve kimlikleri için kullanılan adları tanımlayın. Bunu yapmak için ekleyin bir `Symbols` öğesinde `CommandTable` öğeden sonra `Commands` öğesi.  
  
    ```  
    <Symbols>  
      <!-- Substitute a unique GUID for the placeholder: -->  
      <GuidSymbol name="guidCustomMenuCmdSet"  
        value="{00000000-0000-0000-0000-000000000000}" >  
        <IDSymbol name="grpidMyMenuGroup" value="0x01001"/>  
        <IDSymbol name="cmdidMyContextMenuCommand" value="0x00001"/>  
      </GuidSymbol>  
    </Symbols>  
    ```  
  
5.  Değiştir `{000...000}` menü öğeleri ve grupları tanımlayan bir GUID. Yeni bir GUID almak için kullanın **Create GUID** aracındaki **Araçları** menüsü.  
  
    > [!NOTE]
    >  Daha fazla grup veya menü öğeleri eklerseniz, aynı GUID'ye kullanabilirsiniz. Ancak, yeni değerleri kullanmanız gerekir `IDSymbols`.  
  
6.  Bu yordamdan kopyaladığınız kodda aşağıdaki dizeleri her oluşumu kendi dizelerle değiştirin:  
  
    -   `grpidMyMenuGroup`  
  
    -   `cmdidMyContextMenuCommand`  
  
    -   `guidCustomMenuCmdSet`  
  
    -   `My Context Menu Command`  
  
##  <a name="version"></a> Package.tt paket sürümünü güncelleştir  
 Ekleme veya bir komut değiştirme her güncelleştirme `version` parametresinin <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> uygulanan paketi sınıfına yeni etki alanına özgü dil sürümünü bırakmadan önce.  
  
 Paket sınıfı oluşturulan dosyasında tanımlı olduğundan Package.cs dosyasını oluşturur metin şablonu dosyasını özniteliğinde güncelleştirin.  
  
#### <a name="to-update-the-packagett-file"></a>Package.tt dosyasını güncelleştirmek için  
  
1.  İçinde **Çözüm Gezgini**, **DslPackage** içinde proje **GeneratedCode** klasörü Package.tt dosyasını açın.  
  
2.  Bulun `ProvideMenuResource` özniteliği.  
  
3.  Artırma `version` ikinci parametresi özniteliğin parametresi. İsterseniz, onun amacı, açıkça anımsatmak için parametre adını yazabilirsiniz. Örneğin:  
  
     `[VSShell::ProvideMenuResource("1000.ctmenu", version: 2 )]`  
  
##  <a name="CommandSet"></a> Komut davranışını tanımlayın  
 İçinde DslPackage\GeneratedCode\CommandSet.cs bildirilmiş bir parçalı sınıf uygulanan bazı komutlar, DSL zaten var. Yeni komut eklemek için aynı sınıfın kısmi bildirimi içeren yeni bir dosya oluşturarak bu sınıfı genişletmeniz gerekir. Sınıf genellikle adıdır  *\<YourDslName >*`CommandSet`. Sınıfın adını doğrulama ve içeriğini İnceleme başlamak kullanışlıdır.  
  
 Komut kümesi sınıfı türetilir <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet>.  
  
#### <a name="to-extend-the-commandset-class"></a>CommandSet sınıfı genişletmek için  
  
1.  Çözüm Gezgini'nde, DslPackage proje GeneratedCode klasörünü açın ve CommandSet.tt altında arayın ve oluşturulan dosya CommandSet.cs açın. Ad alanı ve orada tanımlanan ilk sınıfın adını not edin. Örneğin, görebilirsiniz:  
  
     `namespace Company.Language1`  
  
     `{ ...  internal partial class Language1CommandSet : ...`  
  
2.  İçinde **DslPackage**, adlı bir klasör oluşturun **özel kod**. Bu klasörde adlı yeni bir sınıf dosyası oluşturma `CommandSet.cs`.  
  
3.  Yeni dosyasında, aynı ad alanına ve oluşturulan kısmi sınıf ada sahip bir kısmi bildirimini yazma. Örneğin:  
  
     `namespace Company.Language1 /* Make sure this is correct */`  
  
     `{ internal partial class Language1CommandSet { ...`  
  
     **Not** yeni dosyası oluşturmak için sınıf şablonu kullandıysanız, ad alanı ve sınıf adı düzeltmeniz gerekir.  
  
### <a name="extend-the-command-set-class"></a>Komut kümesini sınıfını genişletir  
 Komut kümesi kodunuzu genellikle şu ad alanlarından içe aktarmanız gerekir:  
  
```  
using System;  
using System.Collections.Generic;  
using System.ComponentModel.Design;   
using System.Linq;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Shell;  
```  
  
 Ad alanı ve sınıf adı oluşturulan CommandSet.cs de eşleşecek şekilde ayarlayın:  
  
```  
namespace Company.Language1 /* Make sure this is correct */  
{  
  // Same class as the generated class.  
  internal partial class Language1CommandSet   
  {  
```  
  
 Komutu ne zaman bağlam menüsü ve diğer komutu gerçekleştirmeyi üzerinde görünür olacağını belirlemek için iki yöntem tanımlamak zorunda. Bu yöntemleri geçersiz kılmaları değildir; Bunun yerine, bunları komutların listesini kaydedersiniz.  
  
### <a name="define-when-the-command-will-be-visible"></a>Komut zaman görünür olacak tanımlayın  
 Her komut için tanımlayan bir `OnStatus...` komutu menüsünde olup görünür ve olup, etkinleştirilecek veya devre dışı belirler yöntemi. Ayarlama `Visible` ve `Enabled` özelliklerini `MenuCommand`, aşağıdaki örnekte gösterildiği gibi. Bu yöntem, hızlı bir şekilde çalışması gerekir, böylece kullanıcı Diyagramı sağ tıklatır her zaman kısayol menüsünün oluşturmak için çağrılır.  
  
 Bu örnekte, yalnızca kullanıcının belirli bir tür şeklin seçilmiş ve yalnızca seçilen öğeleri en az biri belirli bir durumda olduğunda etkin olduğunda komut görülebilir. Örnek sınıf diyagramı DSL şablona dayalı ve ClassShape ve ModelClass DSL tanımlanan türleri şunlardır:  
  
```  
private void OnStatusMyContextMenuCommand(object sender, EventArgs e)  
{  
  MenuCommand command = sender as MenuCommand;  
  command.Visible = command.Enabled = false;  
  foreach (object selectedObject in this.CurrentSelection)  
  {  
    ClassShape shape = selectedObject as ClassShape;  
    if (shape != null)  
    {  
      // Visibility depends on what is selected.  
      command.Visible = true;  
      ModelClass element = shape.ModelElement as ModelClass;  
      // Enabled depends on state of selection.  
      if (element != null && element.Comments.Count == 0)  
      {  
        command.Enabled = true;  
        return; // seen enough  
} } } }  
```  
  
 Aşağıdaki parçaları OnStatus yöntemleri sık yararlı olur:  
  
-   `this.CurrentSelection`. Kullanıcı sağ şekli bu listede her zaman dahil edilir. Kullanıcı diyagramı boş bir bölümünü tıklarsa, diyagram listesi yalnızca üyesidir.  
  
-   `this.IsDiagramSelected()` - `true` Kullanıcı diyagramı boş bir kısmına tıkladıysanız.  
  
-   `this.IsCurrentDiagramEmpty()`  
  
-   `this.IsSingleSelection()` -Kullanıcı birden fazla nesne seçmediğiniz  
  
-   `this.SingleSelection` -Şekil veya kullanıcı sağ diyagramı  
  
-   `shape.ModelElement as MyLanguageElement` -bir şekli tarafından temsil edilen model öğesi.  
  
 Genel bir kılavuz olarak olun `Visible` özelliği ne seçili olursa bağlıdır ve olun `Enabled` özellik seçilen öğeleri durumuna bağlıdır.  
  
 Bir OnStatus yöntemi deposu durumunu değiştirmemeniz gerekir.  
  
### <a name="define-what-the-command-does"></a>Komutun ne yaptığını tanımlayın  
 Her komut için tanımlayan bir `OnMenu...` kullanıcı menü komutunu tıkladığında, gerekli bir eylem gerçekleştiren yöntemi.  
  
 Model öğelerine değişiklik yaparsanız, bunu bir işlem içinde yapmanız gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: standart menü komutu değiştirme](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).  
  
 Bu örnekte, `ClassShape`, `ModelClass`, ve `Comment` sınıf diyagramı DSL şablondan türetilen DSL tanımlanan türleridir.  
  
```  
private void OnMenuMyContextMenuCommand(object sender, EventArgs e)  
{  
  MenuCommand command = sender as MenuCommand;  
  Store store = this.CurrentDocData.Store;  
  // Changes to elements and shapes must be performed in a Transaction.  
  using (Transaction transaction =  
       store.TransactionManager.BeginTransaction("My command"))  
  {  
    foreach (object selectedObject in this.CurrentSelection)  
    {  
      // ClassShape is defined in my DSL.  
      ClassShape shape = selectedObject as ClassShape;  
      if (shape != null)  
      {  
        // ModelClass is defined in my DSL.  
        ModelClass element = shape.ModelElement as ModelClass;  
        if (element != null)  
        {  
          // Do required action here - for example:  
  
          // Create a new element. Comment is defined in my DSL.  
          Comment newComment = new Comment(element.Partition);  
          // Every element must be the target of an embedding link.  
          element.ModelRoot.Comments.Add(newComment);  
          // Set properties of new element.  
          newComment.Text = "This is a comment";  
          // Create a reference link to existing object.  
          element.Comments.Add(newComment);  
        }  
      }  
    }  
    transaction.Commit(); // Don't forget this!  
  }  
}  
```  
  
 Nesne nesnesi modelinde gidin ve nesneler ve bağlantılar oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: standart menü komutu değiştirme](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).  
  
### <a name="register-the-command"></a>Register komutu  
 C# dilinde CommandSet.vsct simgeleri bölümünde yapılan GUID ve ID değerleri bildirimlerini Yinele:  
  
```  
private Guid guidCustomMenuCmdSet =   
    new Guid("00000000-0000-0000-0000-000000000000");  
private const int grpidMyMenuGroup = 0x01001;  
private const int cmdidMyContextMenuCommand = 1;  
```  
  
 İçinde eklenmiş olarak aynı GUID değeri kullanır **Commands.vsct**.  
  
> [!NOTE]
>  VSCT dosyasının simgeleri bölümü değiştirirseniz, bu bildirimleri eşleşecek şekilde değiştirmeniz gerekir. Package.tt sürüm numarasını Artır  
  
 Menü komutları bu komut kümesinin bir parçası kaydedin. `GetMenuCommands()` Diyagram zaman başlatıldıktan sonra çağrılır:  
  
```  
protected override IList<MenuCommand> GetMenuCommands()  
{  
  // Get the list of generated commands.  
  IList<MenuCommand> commands = base.GetMenuCommands();  
  // Add a custom command:  
  DynamicStatusMenuCommand myContextMenuCommand =  
    new DynamicStatusMenuCommand(  
      new EventHandler(OnStatusMyContextMenuCommand),  
      new EventHandler(OnMenuMyContextMenuCommand),  
      new CommandID(guidCustomMenuCmdSet, cmdidMyContextMenuCommand));  
  commands.Add(myContextMenuCommand);  
  // Add more commands here.  
  return commands;  
}   
```  
  
## <a name="test-the-command"></a>Test et komutu  
 Derleme ve Visual Studio deneysel örneğinde DSL çalıştırın. Komutu, belirttiğiniz durumlarda kısayol menüsünde görüntülenmelidir.  
  
#### <a name="to-exercise-the-command"></a>Komutu kullanmak için  
  
1.  Üzerinde **Çözüm Gezgini** araç tıklatın **tüm şablonları dönüştürme**.  
  
2.  Tuşuna **F5** çözümü yeniden derleyin ve etki alanına özgü dil Deneysel derlemede hata ayıklamayı Başlat.  
  
3.  Deneysel derlemede örnek diyagramı açın.  
  
4.  Çeşitli öğeleri komutu doğru etkin veya devre dışı bırakıldı ve uygun şekilde gösterilen ya da gizli, seçilen öğeye bağlı olarak olduğunu doğrulamak için diyagramdaki sağ tıklayın.  
  
## <a name="troubleshooting"></a>Sorun giderme  
 **Komut menüsünde görünmez:**  
  
-   Komut DSL paket yükleyene kadar yalnızca Visual Studio Örnekleri hata ayıklamaya görünecektir. Daha fazla bilgi için bkz: [etki alanına özgü dil çözümleri dağıtma](../modeling/deploying-domain-specific-language-solutions.md).  
  
-   Deneysel Örneğiniz için bu DSL doğru dosya adı uzantısına sahip olduğundan emin olun. Dosya adı uzantısı denetlemek için Visual Studio ana örneğinde DslDefinition.dsl açın. Düzenleyici düğüm DSL Explorer'da sağ tıklayın ve ardından Özellikler'i tıklatın. Özellikler penceresinde FileExtension özelliğini inceleyin.  
  
-   Yaptığınız [paket sürüm numarasını Artır](#version)?  
  
-   Bir kesme noktası OnStatus yönteminizi başında ayarlayın. Aşağıdaki diyagramda, herhangi bir bölümünü sağ tıklattığınızda bölün.  
  
     **OnStatus yöntemi çağrılmazsa**:  
  
    -   GUID'ler ve CommandSet kodunuzda kimlikleri Commands.vsct simgeleri bölümünde eşleştiğinden emin olun.  
  
    -   Commands.vsct içinde GUID ve her üst düğüm kimliği doğru üst grubu tanımlayan emin olun.  
  
    -   Visual Studio komut istemi devenv /rootsuffix exp/Setup yazın. Ardından Visual Studio hata ayıklama örneğini yeniden başlatın.  
  
-   Bu komut doğrulamak için OnStatus yöntemle adım. Görünür ve komutu. Etkin ayarlanmıştır true.  
  
 **Yanlış menü metni görünür veya komut yanlış yerde görünür**:  
  
-   GUID ve kimliği birleşimi, bu komut için benzersiz olduğundan emin olun.  
  
-   Paketinin önceki sürümlerini kaldırdığınızdan emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir etki alanına özgü dil kişiselleştirmek için kod yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)   
 [Nasıl yapılır: standart menü komutu değiştirme](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md)   
 [Etki alanına özgü dil çözümlerini dağıtma](../modeling/deploying-domain-specific-language-solutions.md)   
 [Örnek kod: hattı diyagramları](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
 
