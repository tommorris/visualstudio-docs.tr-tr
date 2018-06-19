---
title: 'Nasıl yapılır: oluşturmak bir. Vsct dosya | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, creating
ms.assetid: b955f51c-f9f9-49c3-a8e4-63b6eb0e0341
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c6456b0b866f08956862fa197719354bedf0ecf6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132926"
---
# <a name="how-to-create-a-vsct-file"></a>Nasıl yapılır: oluşturmak bir. Vsct dosyası  
  
Bir XML tabanlı Visual Studio komut tablo yapılandırma (.vsct) dosyası oluşturmak için birkaç yolu vardır.  
  
-   İçinde yeni bir VSPackage oluşturabilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] paketi şablonu.  
  
-   XML tabanlı komut tablo yapılandırma derleyici Vsct.exe, varolan .ctc dosyasından bir dosya oluşturmak için kullanabilirsiniz.  
  
-   Vsct.exe varolan .cto dosyasından bir .vsct dosyası oluşturmak için kullanabilirsiniz.  
  
-   Yeni bir .vsct dosyası el ile oluşturabilirsiniz.  
  
 Bu konuda, el ile bir yeni .vsct dosyasının nasıl oluşturulacağı açıklanmaktadır.  
  
### <a name="to-manually-create-a-new-vsct-file"></a>El ile yeni bir .vsct dosyası oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **dosya**.  
  
3.  İçinde **şablonları** bölmesinde tıklatın **XML dosyası** ve ardından **açık**.  
  
4.  Üzerinde **Görünüm** menüsünde tıklatın **Özellikler penceresini** XML dosyasının özelliklerini görüntülemek için.  
  
5.  İçinde **özellikleri** penceresinde şemaları özellikte Gözat (...) düğmesini tıklatın.  
  
6.  XSD şemaları listesinde vsct.xsd şema seçin. Listede değilse, **Ekle** ve bir yerel sürücüde dosyayı bulun. Tıklatın **Tamam** işiniz bittiğinde.  
  
7.  XML dosyasında yazın `<CommandTable` ve sonra SEKME tuşuna basın. Etiket yazarak kapatın `>`.  
  
     Bu temel .vsct dosyası oluşturur.  
  
8.  Eklemek istediğiniz XML dosyasının öğeleri doldurun, için according [VSCT şema](../../extensibility/vsct-xml-schema-reference.md). Daha fazla bilgi için bkz: [yazma. Vsct dosyaları](../../extensibility/internals/authoring-dot-vsct-files.md)  
  
<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-ctc-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-ctc-file"></a>Nasıl yapılır: oluşturmak bir. Mevcut bir kümeden Vsct dosyası. Ctc dosyası  
  
Varolan komut tablo .ctc kaynak dosyadan bir XML tabanlı .vsct dosyası oluşturabilirsiniz. Bunu yaparak, yeni özelliklerden yararlanabilirsiniz XML tabanlı [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komut tablosu (VSCT) derleyici biçimi.  
  
### <a name="to-create-a-vsct-file-from-a-ctc-file"></a>Bir .ctc dosyasından bir .vsct dosyası oluşturmak için  
  
1.  Perl dil bir kopyasını edinin.  
  
2.  Genellikle bulunan Perl komut dosyasını ConvertCTCToVSCT.pl, bir kopyasını edinin  *\<Visual Studio SDK yükleme yolu >* \VisualStudioIntegration\Tools\bin klasör.  
  
3.  Dönüştürmek istediğiniz .ctc kaynak dosyasının bir kopyasını edinin.  
  
4.  Dosyaları aynı dizine koyun.  
  
5.  İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komut istemi penceresinde, dizine gidin.  
  
6.  Tür  
  
    ```  
    perl.exe ConvertCTCtoVSCT.pl PkgCmd.ctc PkgCmd.vsct  
    ```  
  
     Burada PkgCmd.ctc .ctc dosyasının adını ve PkgCmd.vsct oluşturmak istediğiniz .vsct dosyasının adıdır.  
  
     Bu yeni bir .vsct XML komutu tablo kaynak dosyası oluşturur. Herhangi bir .vsct dosya gibi Vsct.exe, VSCT derleyici kullanarak dosya derleyebilirsiniz.  
  
    > [!NOTE]
    >  XML açıklamaları yeniden biçimlendirme .vsct dosya okunabilirliğini artırabilir.  
  
<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-cto-file"></a>Nasıl yapılır: oluşturmak bir. Mevcut bir kümeden Vsct dosyası. Teknolojiden dosyası  
  
Varolan bir ikili .cto dosyasından bir XML tabanlı .vsct dosyası oluşturabilirsiniz. Bunun yapılması, yeni komutu tablo derleyici biçiminde yararlanmak sağlar. Bu işlem .cto dosya .ctc dosyasından derlenmiş olsa bile çalışır. Düzenle ve başka bir .cto dosyasına .vsct dosyasını derleyin.  
  
### <a name="to-create-a-vsct-file-from-a-cto-file"></a>Bir .cto dosyasından bir .vsct dosyası oluşturmak için  
  
1.  .Cto dosya ve karşılık gelen .ctsym dosya kopyalarını alın.  
  
2.  Dosyaları vsct.exe derleyici ile aynı dizine koyun.  
  
3.  Visual Studio komut isteminde .cto ve .ctsym dosyalarını içeren dizine gidin.  
  
4.  Tür **vsct.exe** *ctofilename *** .cto** * vsctfilename ***.vsct -S***symfilename ***.ctsym**.  
  
     `ctofilename` .cto dosyasının adıdır `vsctfilename` oluşturmak istediğiniz vsct dosyasının adıdır ve `symfilename` .ctsym dosyasının adıdır.  
  
     Bu işlem yeni bir .vsct XML komutu tablo derleyici dosyası oluşturur. Düzenle ve herhangi bir .vsct dosya gibi vsct.exe, vsct derleyici dosyasıyla derleyin.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Yalnızca bir .vsct dosyası projeye ekleme derlemek için neden olmaz. Yapı işleminde içermelidir.  
  
### <a name="to-add-a-vsct-file-to-project-compilation"></a>Proje derleme .vsct dosya eklemek için  
  
1.  Proje dosyanızı düzenleyicisinde açın. Proje yüklüyse, önce bellekten gerekir.  
  
2.  Ekleme bir [ItemGroup öğesi](../../msbuild/itemgroup-element-msbuild.md) aşağıdaki örnekte gösterildiği gibi bir VSCTCompile öğesi içeren.  
  
    ```xml  
    <ItemGroup>  
      <VSCTCompile Include="TopLevelMenu.vsct">  
        <ResourceName>Menus.ctmenu</ResourceName>  
      </VSCTCompile>  
    </ItemGroup>  
  
    ```  
  
     ResourceName öğe her zaman ayarlanmalı `Menus.ctmenu`.  
  
3.  Projeniz .resx dosyası içeriyorsa, MergeWithCTO bir öğe içeren EmbeddedResource öğe aşağıdaki örnekte gösterildiği gibi ekleyin.  
  
    ```xml  
    <EmbeddedResource Include="VSPackage.resx">  
      <MergeWithCTO>true</MergeWithCTO>  
      <ManifestResourceName>VSPackage</ManifestResourceName>  
    </EmbeddedResource>  
  
    ```  
  
     Bu biçimlendirme katıştırılmış kaynakları içeren ItemGroup öğesi içinde gitmeniz gerekir.  
  
4.  Genellikle paket dosyasını açın *ProjectName*Package.cs veya *ProjectName*Düzenleyicisi'nde Package.vb.  
  
5.  Aşağıdaki örnekte gösterildiği gibi bir ProvideMenuResource özniteliği paketi sınıfına ekleyin.  
  
    ```csharp  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    ```  
  
     İlk parametre değeri proje dosyasında tanımlanan KaynakAdı özniteliğinin değeri aynı olmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazma. Vsct dosyaları](../../extensibility/internals/authoring-dot-vsct-files.md)   
 [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md)