---
title: "VSCT derleyici komut satırı bayrakları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT files, compiling
- command-table file compilation (VSCT files)
ms.assetid: 9dc6c33f-e6cf-4cf2-9b05-e8f7bfac1cfb
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fd18d04adfbf3acd0ca50c1e75bd2a1694b28721
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="vsct-compiler-command-line-flags"></a>VSCT derleyici komut satırı bayrakları
Visual Studio komut tablosu (VSCT) derleyici .vsct dosyaları başarılı derlenmesini emin olmak için komut satırı anahtarları sağlar.  
  
## <a name="command-line-parameters"></a>Komut satırı parametreleri  
 Temel VSCT Yardım'dan görüntülemek için bir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **komutu** penceresinde gidin *Visual Studio SDK yükleme yolu*\VisualStudioIntegration\Tools\Bin\ klasörü ve türü:  
  
```  
vsct /?  
```  
  
 Bu döndürür:  
  
```  
Microsoft (R) Visual Studio (R) Command Table Compiler Version 3.00.2000  
  
Syntax: vsct <infile> [<outfile>] [-S[symbols file]] [-D<preprocessor-define>]*  
[-I<include-path>]* [-L<language>] [-E[C|H|N]:<name>]  
  
  -D    Specify any additional preprocessor defines  
  -I    Indcate what additional include paths to send to the preprocessor  
  -L    Specify the langauge to use when selecting strings  
  -E    Emit C# objects in the specified namespace for command items,  
        folowed by [L|F|H|N]:<value>  
        F = Name of the file to emit (used if -EL is provided)  
        L = Name of a language providing a CodeDOM provider  
        N = namespace (required if -EL is provided)  
        H = C++ header  
  -c    Clean build skipping dependancy checks  
  -v    Verbose output  
```  
  
> [!NOTE]
>  Karakterler - (tire) ve / (eğik çizgi) komut satırı parametreleri belirten için kabul edilen hem gösterimdir.  
  
 Kabul edilebilir bayrakları ve anlamları şu şekildedir.  
  
|Anahtar|Açıklama|  
|------------|-----------------|  
|-D|Ek tanımlanmış semboller belirtin.|  
|-I|Ek başvurulara çözülürken kullanılmalıdır yol eklemeyi gösterir.|  
|-L|Belirtin <xref:System.Globalization.CultureInfo> kültür adı, örneğin "en-US".|  
|-E|C# nesnelerini [C &#124; tarafından izlenen komutu öğeleri için belirtilen ad alanında yayma H &#124; N]:*filename*burada C C#, H = C++ üstbilgi, N = ad alanı =. Ad alanı, C# için gereklidir.|  
|-v|Ayrıntılı çıktı.|  
  
 -L anahtara karşılık gelen ikili .cto dosya oluşturmak için dizelerin bir grup seçmek için derleyiciye verilen <xref:System.Globalization.CultureInfo> kültür adı. Belirtilen kültür adı bir veya daha fazla dil özniteliği eşleşmelidir [dizeleri öğesi](../../extensibility/strings-element.md) .vsct dosyasında. Dizeleri öğenin hiçbir Language özniteliği varsa içeren öğesinden devralındı [CommandTable öğesi](../../extensibility/commandtable-element.md).  
  
 .Vsct dosyasında birden çok dize öğesi olabilir ve her farklı bir dil öznitelik olabilir. Genelleştirme VSCT derleyici birden çok kez çalıştırma ve her bir kültür adı için -M anahtarı değiştirerek elde edilir.  
  
 -L anahtar tarafından belirtilen kültür adı herhangi bir dize öğesi Language özniteliği eşleşmiyorsa derleyici dil ve bölge eşleşecek şekilde çalışacaktır. Örneğin, "en-US" bulunamazsa derleyici "tr" Bunun yerine çalışacaktır. Başarısız olan, işletim sisteminin geçerli kültür çalışacaktır. Başarısız olan, bulduğu ilk dizeleri öğesi derlenir.  
  
 -E anahtar komutu tablosu tarafından kullanılan sembolleri içeren bir C-style üstbilgi dosyası yayma ya da komut simgeleri nesneleri içeren bir C# dosyası yaymak üzere kullanılabilir.  
  
 -D ve - ı anahtarları aynı ada sahip Cl.exe C önişlemci bayrakları sözdizimi vardır. -D X = Y biçimine sahip tanımları XML tabanlı genişlemesi için kullanılan \<tanımlanan > içinde testleri `Condition` öznitelikleri. -I yol eklemeyi çözümlemek için kullanılan \<Ekle >, \<Extern > ve \<bit eşlem > dosya başvuruları. Daha fazla bilgi için bkz: [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md).  
  
 VSCT derleyici de önceden oluşturulmuş bir ikili dosya uygulayamaz. Bunu yapmak için bir ikili dosya için tedarik \<GirişDosyası >.   İkili dosya VSCT derleyici tarafından üretilen, zaten ekli kendi simgeleri olacaktır ve çıktı simgesel adları ile oluşturur bir \<simgeleri > çıkış bölümü. İkili CTC derleyici tarafından üretilen, çıktı gerçek GUID'ler ve kimliklerini içerir. Geçerli Ctc.exe sürümleri tarafından üretilen *.ctsym dosya ikili giriş dosyası ile aynı klasörde ise, simgeler bu dosyasından yüklenen ve çıktısı için kullanılacak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md)   
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)