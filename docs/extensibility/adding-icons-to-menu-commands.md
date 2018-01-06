---
title: "Menü komutlarına simgeler ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- icons [Visual Studio], adding to toolbars
- toolbars [Visual Studio], adding icons to commands
- commands [Visual Studio], adding icons
ms.assetid: 362a0c7e-5729-4297-a83f-1aba1a37fd44
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 06d90b5174cc9ff2d09d7ccba8b2f39bc1d2a077
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-icons-to-menu-commands"></a>Menü komutlarına simgeler ekleme
Komutları, menüleri ve araç çubuklarında yer alabilir. Araç çubuklarında, bir komut genellikle bir simge ve metin ile görünür (alanından tasarruf etmek için) yalnızca bir simgeyle sırasında menülerde görüntülenecek komutu için yaygın bir sorundur.  
  
 Simgeler 16 piksel genişliğinde 16 piksel yüksek ve 8 bit renk derinliği (256 renk) veya 32 bit renk derinliği (gerçek renk) olabilir. 32-bit renk simgeler tercih edilir. Birden çok bit eşlemler izin verse simgeler genellikle tek bir bit eşlem tek yatay bir satırda halinde düzenlenir. Bit eşlem'i kullanılabilir tek tek simgeler birlikte .vsct dosyasında bu bit eşlemi bildirildi. Başvuru için bkz: [bit eşlemler öğesi](../extensibility/bitmaps-element.md) daha fazla ayrıntı için.  
  
## <a name="adding-an-icon-to-a-command"></a>Simge bir komut ekleme  
 Aşağıdaki yordam, menü komutu ile varolan VSPackage projesine sahip olduğunuzu varsayar. Bunu yapmak nasıl öğrenmek için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
1.  Bir bit eşlem renk derinliği 32-bit oluşturun. Bir simge her zaman 16 x 16 Bu bit eşlemi 16 piksel yüksek olması gerekir ve birden çok 16 piksel genişliğinde bulunur.  
  
     Her bir simgenin tek bir satır birbirine eşleminde yerleştirilir. Alfa kanal her simge saydamlık yerleri belirtmek için kullanın.  
  
     Bir 8 bit renk derinliği kullanıyorsanız macenta kullanın `RGB(255,0,255)`, saydam olarak. Ancak, 32-bit renk simgeler tercih edilir.  
  
2.  Simge dosyası VSPackage projenizdeki kaynakları dizinine kopyalayın. Çözüm Gezgini'nde projeye simgesini ekleyin. (Kaynakları, seçin ve Ekle sonra da var olan öğenin bağlam menüsünde tıklatın ve simge dosyası seçin.)  
  
3.  .Vsct dosyayı düzenleyicide açın.  
  
4.  Ekleme bir `GuidSymbol` öğesi adıyla **testIcon**. Bir GUID oluşturun (**araçları / Create GUID**seçeneğini belirleyip **kayıt defteri biçimi** Kopyala'yı tıklatın) ve yapıştırın `value` özniteliği. Sonuç aşağıdaki gibi görünmelidir:  
  
    ```xml  
    <!-- Create your own GUID -->  
    <GuidSymbol name="testIcon" value="{00000000-0000-0000-0000-0000}">  
    ```  
  
5.  Ekleme bir `<IDSymbol>` simge. `name` Özniteliktir simgenin kimliği ve `value` varsa şeridindeki konumunu gösterir. Yalnızca bir simge ise 1 ekleyin. Sonuç aşağıdaki gibi görünmelidir:  
  
    ```xml  
    <!-- Create your own GUID -->  
    <GuidSymbol name="testIcon" value="{00000000-0000-0000-0000-0000}">  
        <IDSymbol name="testIcon1" value="1" />  
    </GuidSymbol>  
    ```  
  
6.  Oluşturma bir `<Bitmap>` içinde `<Bitmaps>` .vsct dosyasının simgeleri içeren bit eşlemi temsil eder.  
  
    -   Ayarlama `guid` adını değerine `<GuidSymbol>` önceki adımda oluşturduğunuz öğesi.  
  
    -   Ayarlama `href` bit eşlem dosyası göreli yolunu değerine (Bu durumda **kaynakları\\< simgesinin dosya adı\>**.  
  
    -   Ayarlama `usedList` daha önce oluşturduğunuz IDSymbol değerine. Bu öznitelik VSPackage kullanılacak simgeleri virgülle ayrılmış listesini belirtir. Listede olmayan simgeler dışlanan form derleme ' dir.  
  
         Bit eşlem blok aşağıdaki gibi görünmelidir:  
  
        ```xml  
        <Bitmap guid="testIcon" href="Resources\<icon file name>" usedList="testIcon1"/>  
        ```  
  
7.  Varolan `<Button>` öğe, ayarladığınız `Icon` daha önce oluşturduğunuz GUIDSymbol ve IDSymbol değerleri öğesine. Bu değerleri içeren bir düğme öğesi bir örneği burada verilmiştir:  
  
    ```xml  
    <Button guid="guidAddIconCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">  
        <Parent guid="guidAddIconCmdSet" id="MyMenuGroup" />  
        <Icon guid="testIcon" id="testIcon1" />  
        <Strings>  
            <ButtonText>My Command name</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
8.  Simge sınayın. Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneğinde Bul komutu. Eklediğiniz bu simgeyi göstermesi gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md)   
 [VSCT XML Şeması Başvurusu](../extensibility/vsct-xml-schema-reference.md)