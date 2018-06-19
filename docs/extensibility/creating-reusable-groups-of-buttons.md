---
title: Yeniden kullanılabilir grupları düğmelerini oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- button groups, creating in VSPackages
- VSPackages, creating reusable button groups
- buttons, creating reusable groups
ms.assetid: 0c561617-fb86-476d-8bd1-c6e5e7464c65
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 97ee7cc2ec63a94036472ccce07b1dc9fa736504
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102986"
---
# <a name="creating-reusable-groups-of-buttons"></a>Düğmelerinin yeniden kullanılabilir grupları oluşturma
Komut grubu, her zaman birlikte menüsü veya araç çubuğunda görünen komutlarını koleksiyonudur. Herhangi bir komut grubu farklı bir üst menüleri .vsct dosyasının CommandPlacements bölümünde atayarak yeniden kullanılabilir.  
  
 Komut grupları genellikle düğmelerini içerir, ancak aynı zamanda diğer menüleri veya birleşik giriş kutuları içerebilirler.  
  
### <a name="to-create-a-reusable-group-of-buttons"></a>Düğmeleri yeniden kullanılabilir bir grup oluşturmak için  
  
1.  Adlı VSIX proje oluşturma `ReusableButtons`. Daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Proje açıldığında adlı bir özel komut öğesi şablonu Ekle **ReusableCommand**. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# / genişletilebilirlik** seçip **özel komut**. İçinde **adı** alan penceresinin alt kısmında, komut dosyası adı Değiştir **ReusableCommand.cs**.  
  
3.  .Vsct dosyasında simgeleri bölümüne gidin ve grupları ve proje için komutları içeren GuidSymbol öğesi bulunamıyor. GuidReusableCommandPackageCmdSet adlı.  
  
4.  Aşağıdaki örnekte olduğu gibi grubuna ekleyecek her düğme için bir IDSymbol ekleyin.  
  
    ```xml  
    <GuidSymbol name="guidReusableCommandPackageCmdSet" value="{7f383b2a-c6b9-4c1d-b4b8-a26dc5b60ca1}">  
        <IDSymbol name="MyMenuGroup" value="0x1020" />  
        <IDSymbol name="ReusableCommandId" value="0x0100" />  
        <IDSymbol name="SecondReusableCommandId" value="0x0200" />  
    </GuidSymbol>  
    ```  
  
     Varsayılan olarak, komut öğe şablonu adlı bir grup oluşturur **MyMenuGroup** ve her bir IDSymbol girişi ile birlikte sağlanan adına sahip bir düğme.  
  
5.  Grupları bölümünde simgeleri bölümünde verilen olanları aynı GUID ve ID özniteliklere sahip bir Grup öğesi oluşturun. Ayrıca, varolan bir grubu kullanın veya aşağıdaki örnekteki gibi komut şablonu tarafından sağlanan girdi kullanabilirsiniz. Bu grubun görünür **Araçları** menüsü  
  
    ```xml  
    <Groups>  
        <Group guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">  
              <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_TOOLS"/>  
        </Group>  
    </Groups>  
    ```  
  
### <a name="to-create-a-group-of-buttons-for-reuse"></a>Düğmeleri yeniden kullanım için bir grup oluşturmak için  
  
1.  Komutun veya menü tanımındaki bir üst grubun kullanarak ya da koyarak komut veya menü grubunda CommandPlacements bölümünü kullanarak, bir gruptaki bir komut veya menü koyabilirsiniz.  
  
     Düğmeleri bölümünde grubunuzun üst olarak sahip bir düğme tanımlayın veya aşağıdaki örnekte gösterildiği gibi paketi şablonu tarafından sağlanan düğmesini kullanın.  
  
    ```xml  
    <Button guid="guidReusableCommandPackageCmdSet" id="ReusableCommandId" priority="0x0100" type="Button">  
        <Parent guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke ReusableCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
2.  Bir düğme birden fazla grubunda bulunmasını istiyorsanız, bir giriş için komutları bölümünden sonra yerleştirilmelidir CommandPlacements bölümündeki oluşturun. CommandPlacement öğenin yerleştirmek istediğiniz düğmesinin eşleştiğinden GUID ve kimliği özniteliklerini ayarlayın ve ardından GUID ve üst öğesi Kimliğini bu hedef grubun aşağıdaki örnekte gösterildiği gibi ayarlayın.  
  
    ```xml  
    <CommandPlacements>  
        <CommandPlacement guid="guidReusableCommandPackageCmdSet" id="SecondReusableCommandId" priority="0x105">  
          <Parent guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" />  
        </CommandPlacement>  
    </CommandPlacements>  
    ```  
  
    > [!NOTE]
    >  Öncelik alanın değerini yeni komut grubu komutu konumunu belirler. Öğe öğe tanımında ayarlamak geçersiz kılar CommandPlacement önceliklerini ayarlayın. Düşük öncelikli işler değerlere sahip komutları önce daha yüksek öncelik değerine sahip komutlar görüntülenir. Yinelenen öncelik değerleri izin verilir, ancak aynı öncelik değerine sahip komutları göreli konumunu, çünkü garanti edilemez hangi sırayla **devenv/Setup** komut kayıt defterinden son arabirimi oluşturur tutarlı olmayabilir.  
  
### <a name="to-put-a-reusable-group-of-buttons-on-a-menu"></a>Menüde düğmelerinin yeniden kullanılabilir bir grup yerleştirilecek  
  
1.  Girdi oluşturma `CommandPlacements` bölümü. GUID ve Kimliğini ayarlamak `CommandPlacement` olanlar, grubunuzun öğesine ve üst GUID ve ID olanlar hedef konumu ayarlayın.  
  
     CommandPlacements bölüm yalnızca komutları bölümünden sonra yerleştirilmelidir:  
  
    ```xml  
    <CommandTable>  
    ...  
      <Commands>... </Commands>  
      <CommandPlacements>... </CommandPlacements>  
    ...   
    </CommandTable>  
    ```  
  
     Komut grubu birden fazla menüsünde dahil edilebilir. Ana menü, oluşturduğunuz tarafından sağlanan bir olabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] (olarak açıklanan ShellCmdDef.vsct veya SharedCmdDef.vsct), ya da başka bir VSPackage tanımlanmış. Ana menü sonunda bağlı olduğu sürece ana öğe Katmanlar sınırsız sayısıdır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] veya VSPackage tarafından görüntülenen bir kısayol menüsü.  
  
     Aşağıdaki örnek Grup koyar **Çözüm Gezgini** diğer düğmeleri sağındaki araç.  
  
    ```xml  
    <CommandPlacements>  
        <CommandPlacement guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" priority="0xF00">  
          <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN"/>  
        </CommandPlacement>  
    </CommandPlacements>  
    ```  
  
    ```xml  
    <CommandPlacements>  
      <CommandPlacement guid="guidButtonGroupCmdSet" id="MyMenuGroup"   
          priority="0x605">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_TOOLS" />  
      </CommandPlacement>  
    </CommandPlacements>  
  
    ```
