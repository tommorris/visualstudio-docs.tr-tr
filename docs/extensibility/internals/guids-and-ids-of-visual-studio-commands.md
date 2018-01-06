---
title: "GUID ve Visual Studio komutları kimliklerini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands
- id
- command placement
- visual studio command
- guid
ms.assetid: 2ea4bee2-0259-4675-8e65-2023b312b516
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 44ae5ff7e9095d6c88d753342da30983b30b7364
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="guids-and-ids-of-visual-studio-commands"></a>GUID ve Visual Studio komut kimlikleri
Visual Studio tümleşik geliştirme ortamı (IDE) dahil komutların GUID ve ID değerleri, Visual Studio SDK'sı bir parçası olarak yüklenen .vsct dosyalarında tanımlanır. Daha fazla bilgi için bkz: [IDE-Defined komutlar, menüler ve grupları](../../extensibility/internals/ide-defined-commands-menus-and-groups.md).  
  
 .Vsct dosyalarında tanımlanan IDE nesneleri ile çalışma hakkında daha fazla bilgi için bkz: [genişletme menüleri ve komutları](../../extensibility/extending-menus-and-commands.md).  
  
## <a name="finding-a-command-definition"></a>Bir komut tanımı bulma  
 Visual Studio birden fazla bin komutları tanımladığından, tüm burada listelemek için zordur. Bunun yerine, bir komut tanımı bulmak için aşağıdaki adımları izleyin.  
  
#### <a name="to-locate-a-command-definition"></a>Bir komut tanımı bulmak için  
  
1.  Aşağıdaki dosyalarda Visual Studio'da açın *Visual Studio SDK yükleme yolu*\VisualStudioIntegration\Common\Inc\ klasörü: SharedCmdDef.vsct, ShellCmdDef.vsct, VsDbgCmdUsed.vsct, Venusmenu.vsct.  
  
     Visual Studio komutların çoğu SharedCmdDef.vsct ve ShellCmdDef.vsct tanımlanır. Hata ayıklayıcı için ilgilidir komutları VsDbgCmdUsed.vsct tanımlar ve Web geliştirme için belirli komutları Venusmenu.vsct tanımlar.  
  
2.  Komutu bir menü öğesini menü öğesinin tam metin unutmayın. Komut bir araç çubuğunda ise üzerinde duraklattığınızda görüntülenen araç ipucu metni unutmayın.  
  
3.  Açmak için CTRL + F tuşlarına basın **Bul** iletişim kutusu.  
  
4.  İçinde **Aranan** 2. adımda not ettiğiniz metin yazın.  
  
5.  Doğrulayın **tüm açık belgeleri** görüntülenen **konum** kutusu.  
  
6.  Tıklatın **Sonrakini Bul** metin seçildiyse kadar düğme `<Strings>` bölümünü bir [Button öğesi](../../extensibility/button-element.md).  
  
     `<Button>` Komutu görünen öğedir komut tanımı.  
  
 Komut tanımı bulduğunuzda, komutu bir kopyasını başka bir menü veya araç çubuğunda oluşturarak koyabilirsiniz bir [CommandPlacement öğesi](../../extensibility/commandplacement-element.md) aynı olan `guid` ve `id` değerleri olarak komutu. Daha fazla bilgi için bkz: [, yeniden kullanılabilir grupları düğmeler oluşturma](../../extensibility/creating-reusable-groups-of-buttons.md).  
  
### <a name="special-cases"></a>Özel durumlar  
 Aşağıdaki durumlarda menü metni veya araç ipucu metni tam komut tanımı'nda nedir eşleşmiyor olabilir.  
  
-   Altı çizili bir karaktere gibi içeren menü öğeleri **yazdırma** komutunu **dosya** menüsünde, P çizilir.  
  
     Menü öğesi adlarında '&' karakteri koyarak karakter görüntülenir altı çizili olarak. Ancak, özel karakterler belirtmek için '&' karakteri kullanır ve görüntülenecek olan ve işareti yazılmalıdır olduğunu gerektirir, XML .vsct dosyaları yazılmış olarak&amp;'. Bu nedenle, bir dosyadaki .vsct **P**azdır komutu görünür olarak '&amp;yazdırma '.  
  
-   Dinamik metin sahip komutları **kaydetmek** *geçerli Filename*ve dinamik olarak üretilen öğeler gibi menü öğeleri üzerindeki **son kullanılan dosyalar** listesi.  
  
     Dinamik metin araması yapmak için güvenilir bir yolu yoktur. Bunun yerine, istenen komut bakarak barındıran Grup bulma [GUID ve Visual Studio menüleri kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) veya [GUID ve kimlikleri, Visual Studio araç çubukları](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)ve arama söz konusu grubun kimliği. Komut tanımı grup olarak yoksa kendi [üst öğesi](../../extensibility/parent-element.md), SharedCmdPlace.vsct ve ShellCmdPlace.vsct (veya hata ayıklayıcı komutlarını VsDbgCmdPlace.vsct) arama bir `<CommandPlacement>` üst ayarlar öğesi komutu. SharedCmdPlace.vsct, ShellCmdPlace.vsct, andVsDbgCmdPlace.vsct olan *Visual Studio SDK yükleme yolu*\VisualStudioIntegration\Common\Inc\ klasör.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md)   
 [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md)