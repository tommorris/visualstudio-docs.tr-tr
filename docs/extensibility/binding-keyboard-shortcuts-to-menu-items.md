---
title: "Menü öğeleri için klavye kısayolları bağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- keyboard command
- keyboards
- command key
- keyboard shortcuts
- menu items
ms.assetid: 19f483b6-4d3e-424e-9d68-dc129c788e47
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1fe1c0bb9c3028c70e1be9df9af1de3b0804844e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="binding-keyboard-shortcuts-to-menu-items"></a>Menü öğeleri bağlama klavye kısayolları
Bir özel menü komutu bir klavye kısayolu bağlamak için yalnızca paketi için .vsct dosyasına bir giriş ekleyin. Bu konuda, bir klavye kısayolu özel düğme, menü öğesi veya araç çubuğu komutuna eşleme ve varsayılan düzenleyicisinde klavye eşleme uygulamak veya özel bir düzenleyici sınırlamak nasıl açıklanmaktadır.  
  
 Mevcut Visual Studio menü öğeleri için klavye kısayolları atamak için bkz: [tanımlama ve özelleştirme klavye kısayolları](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
## <a name="choosing-a-key-combination"></a>Bir tuş bileşimini seçme  
 Birçok klavye kısayolları Visual Studio'da zaten kullanıldı. Yinelenen bağlamaları algılamak sabit olduğundan ve ayrıca öngörülemeyen sonuçlara neden olabilir, aynı kısayolu birden fazla komut atamanız gerekir değil. Bu nedenle, onu atamadan önce bir kısayol kullanılabilirliğini doğrulamak için bir fikirdir.  
  
#### <a name="to-verify-the-availability-of-a-keyboard-shortcut"></a>Klavye kısayolu kullanılabilirliğini doğrulamak için  
  
1.  İçinde **Araçlar / Seçenekler / ortamı** penceresinde, seçin **klavye**.  
  
2.  Olduğundan emin olun **kullanım yeni kısayoluna** ayarlanır **genel**.  
  
3.  İçinde **basın kısayol tuşları** kutusuna, kullanmak istediğiniz klavye kısayolu yazın.  
  
     Visual Studio'da kısayol zaten kullanılıyorsa **şu anda kullandığı Shorcut** kutusunu kısayol şu anda çağıran komut gösterir.  
  
4.  Eşlenmedi tane bulana kadar farklı tuş birleşimlerini deneyin.  
  
    > [!NOTE]
    >  ALT kullanan klavye kısayolları menüsünü açın ve doğrudan komut yürütme olabilirsiniz. Bu nedenle, **şu anda kullandığı Shorcut** ALT içeren bir kısayol yazdığınızda kutusu boş olabilir. Kısayol menü tarafından kapanış açmaz doğrulayabilirsiniz **seçenekleri** iletişim kutusunu ve ardından tuşlarına basarak.  
  
 Aşağıdaki yordam, menü komutu ile varolan bir VSPackage sahip olduğunuzu varsayar. Bunu yardıma gereksinim duyarsanız bir göz atalım [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
#### <a name="to-assign-a-keyboard-shortcut-to-a-command"></a>Komut bir klavye kısayolu atamak için  
  
1.  Paketinizi .vsct dosyasını açın.  
  
2.  Boş bir oluşturma `<KeyBindings>` sonra bölümünde `<Commands>` zaten mevcut değilse.  
  
    > [!WARNING]
    >  Anahtar bağlama hakkında daha fazla bilgi için bkz: [Keybinding](../extensibility/keybinding-element.md).  
  
     İçinde `<KeyBindings>` bölümünde, oluşturmak bir `<KeyBinding>` girişi.  
  
     Ayarlama `guid` ve `id` öznitelikleri olanlar istediğiniz çağrılacak komutu.  
  
     Ayarlama `mod1` özniteliğini **denetim**, **Alt**, veya **Shift**.  
  
     Taşıyan bölüm aşağıdakine benzer görünmelidir:  
  
    ```xml  
    <KeyBindings>  
        <KeyBinding guid="<name of command set>" id="<name of command id>"  
            editor="guidVSStd97" key1="1" mod1="CONTROL"/>  
    </KeyBindings>  
  
    ```  
  
 Klavye kısayolu ikiden fazla anahtarları gerektiriyorsa, ayarlamak `mod2` ve `key2` öznitelikleri.  
  
 Çoğu durumda, **Shift** zaten tuşuna basarak bir büyük harf ya da bir simge türünü çoğu alfasayısal anahtarları neden olduğundan ikinci değiştiricisi kullanılmamalıdır.  
  
 Sanal anahtar kodları erişim, örneğin, işlev tuşlarını ilişkili bir karakter olmayan özel anahtarları olanak tanır ve **geri** anahtarı. Daha fazla bilgi için bkz: [sanal anahtarı kodları](http://go.microsoft.com/fwlink/?LinkID=105932).  
  
 Komut Düzenleyicisi Visual Studio içinde kullanılabilir hale getirmek ayarlamak `editor` özniteliğini `guidVSStd97`.  
  
 Komutu yalnızca özel bir düzenleyici kullanılabilir yapmak için ayarlanmış `editor` özniteliği tarafından oluşturulan özel düzenleyici adına [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] paket VSPackage oluştururken şablonu özel düzenleyici içerir. Ad değerini bulmak için konum `<Symbols>` bölümünde bir `<GuidSymbol>` düğümü, `name` özniteliği bitiyor "`editorfactory`." Özel düzenleyici adıdır.  
  
## <a name="example"></a>Örnek  
 Bu örnek CTRL + ALT + C klavye kısayolu adlı bir komut bağlar `cmdidMyCommand` adlı bir pakete `MyPackage`.  
  
```  
<CommandTable>  
. . .  
<Commands>  
. . .  
</Commands>  
<KeyBindings>  
  <KeyBinding guid="guidMyPackageCmdSet" id="cmdidMyCommand"   
      key1="C" mod1="CONTROL" mod2="ALT" editor="guidVSStd97" />  
</KeyBindings>  
. . .  
</CommandTable>  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek klavye kısayolu CTL + B adlı bir komut bağlar `cmdidBold` adlı bir projede `TestEditor`. Komut, yalnızca özel Düzenleyicisi'nde alan ve diğer düzenleyicileri kullanılabilir.  
  
```xml  
<KeyBinding guid="guidVSStd97" id="cmdidBold" editor="guidTestEditorEditorFactory" key1="B" mod1="Control" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md)