---
title: Eski dil Service2 kaydetme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- registration, language services
- language services, registry information
- registry, language services
ms.assetid: ca312aa3-f9f1-4572-8553-89bf3a724deb
caps.latest.revision: "24"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 364b17e6759d0ca337b69c89c51dfba8d26f3e32
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="registering-a-legacy-language-service"></a>Eski dil hizmeti kaydetme
Aşağıdaki bölümler kayıt defteri girdileri listesi çeşitli dil için kullanılabilir hizmet seçenekleri sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Kayıt defteri girdileri aşağıdaki listede *VS Reg kök* HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio için eşittir\\*X.Y*, burada *X.Y* olduğu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sürüm numarası.  
  
## <a name="registry-entries-for-language-service-options"></a>Dil hizmeti seçenekleri için kayıt defteri girişleri  
 *VS Reg kök*\Languages\Language Hizmetleri\\*dil adı* anahtarı, aşağıdaki değerleri içerebilir.  
  
|Ad|Tür|Aralık|Açıklama|  
|----------|----------|-----------|-----------------|  
|(Varsayılan)|REG_SZ|*\<GUID >*|Dil hizmetinin GUID.|  
|LangResID|REG_DWORD|0x0 0xffff|Dil yerelleştirilmiş metin adı için kaynak tanımlayıcısı (ResID) dize.|  
|Paket|REG_SZ|*\<GUID >*|VSPackage GUID.|  
|ShowCompletion|REG_DWORD|0-1|Belirtir olup olmadığını **deyim tamamlama** içinde seçenekleri **seçenekleri** iletişim kutusu etkinleştirilir.|  
|ShowSmartIndent|REG_DWORD|0-1|Belirtir olup olmadığını belirleme seçeneği **akıllı** içinde girintileme **seçenekleri** iletişim kutusu etkindir.|  
|RequestStockColors|REG_DWORD|0-1|Belirtir özel olup olmadığını veya varsayılan renkleri anahtar sözcükleri renk için kullanılır.|  
|ShowHotURLs|REG_DWORD|0-1|Kullanıcıyı URL'leri tıklatın olup olmadığını belirtir.|  
|Etkin olmayan URL'lere varsayılan|REG_DWORD|0-1|İlk ayarını belirtir **etkinleştirmek tek tıklamayla URL Gezinti** seçeneğini **seçenekleri** iletişim kutusu.|  
|DefaultToInsertSpaces|REG_DWORD|0-1|Dil hizmeti "alanları, varsayılan sekmesini seçeneği olarak Ekle" olup olmadığını belirtir.|  
|ShowDropdownBarOption|REG_DWORD|0-1|Etkinleştirir veya devre dışı bırakır **gezinti çubuğu** seçeneğini **seçenekleri** gösterir veya gizler iletişim kutusunu **gezinti çubuğu**.|  
|Yalnızca tek bir kod penceresi|REG_DWORD|0-1|Etkinleştirir veya devre dışı bırakır **yeni pencere** içinde seçim **penceresi** dil hizmeti menüsü.|  
|EnableAdvancedMembersOption|REG_DWORD|0-1|Etkinleştirir veya devre dışı bırakan bir **seçenekleri** iletişim kutusu ayarını **Gelişmiş üyeler Gizle**.|  
|Destek CF_HTML|REG_DWORD|0-1|Düzenleyicisi HTML veri kopyalama ve yapıştırma sağlar olup olmadığını belirtir.|  
|EnableLineNumbersOption|REG_DWORD|0-1|Belirtir olup olmadığını **satır numaraları** içinde seçenekleri **seçenekleri** iletişim kutusu için bir dil hizmeti etkindir.|  
|HideAdvancedMembersByDefault|REG_DWORD|0-1|Özel alanları gibi gelişmiş üyeler detamamlanma listeleri gizlenip gizlenmeyeceğini belirtir.|  
|ShowBraceCompletion|REG_DWORD|0-1|Belirtir olup olmadığını **ayracı tamamlama** seçeneğini **seçenekleri** iletişim kutusu etkindir.|  
  
### <a name="example"></a>Örnek  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      C/C++\  
        (Default)             = reg_sz:{B2F072B0-ABC1-11D0-9D62-00C04FD9DFD9}  
        LangResID             = reg_dword:0x00000000  
        Package               = reg_sz:{8C2EA640-ABC1-11D0-9D62-00C04FD9DFD9}  
        ShowCompletion        = reg_dword:0x00000001  
        ShowSmartIndent       = reg_dword:0x00000001  
        ShowDropdownBarOption = reg_dword:0x00000001  
```  
  
## <a name="registry-entries-for-debugger-languages-options"></a>Hata ayıklayıcı dilleri seçenekleri için kayıt defteri girişleri  
 *VS Reg kök*\Languages\Language Hizmetleri\\*dil adı*\Debugger diller\\*GUID*\ anahtarı, aşağıdakileri içerebilir değerler.  
  
|Ad|Tür|Aralık|Açıklama|  
|----------|----------|-----------|-----------------|  
|(Varsayılan)|REG_SZ|metin|Varsayılan değer dilin adını belge için kullanılabilir. Bu anahtarın adını karşılık gelen bir girişe sahip bir ifade değerlendiricisi GUID'dir  *\<VS Reg kök >*\AD7Metrics\Expression değerlendirici.|  
  
### <a name="example"></a>Örnek  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      C/C++\  
        Debugger Languages\  
          {3A12D0B7-C26C-11D0-B442-00A0244A1DD2}\  
            (Default) = reg_sz:C++  
```  
  
## <a name="registry-entries-for-editor-tools-options"></a>Kayıt defteri girdilerini Düzenleyicisi araç seçenekleri  
 Özellik sayfaları ve özellik düğümleri EditorToolsOptions anahtarı altındaki kayıt defteri anahtarlarını ekleyebilirsiniz. Bu anahtarları ve değerleri özellik sayfalarında tanımlamak **seçenekleri** iletişim kutusu (üzerinde **Araçları** menüsü) dil hizmeti yapılandırmak için kullanılır. Aşağıdaki örnekte, *sayfa adı* bir özellik sayfası adıdır ve *düğüm adı* ağacında bir düğümü üzerinde adıdır **seçenekleri** iletişim kutusu. Sayfa girişi ve düğüm girişi ayrı olarak belirtilmelidir.  
  
|Ad|Tür|Aralık|Açıklama|  
|----------|----------|-----------|-----------------|  
|(Varsayılan)|REG_SZ|resID|Bu seçenek sayfa yerelleştirilmiş görünen adı. Ad metin dizesi veya # olabilir`nnn`, burada `nnn` belirtilen VSPackage DLL uydu bir dize kaynak kimliğidir.|  
|Paket|REG_SZ|*GUID*|Bu seçenekler sayfası uygulayan VSPackage GUID.|  
|Sayfa|REG_SZ|*GUID*|VSPackage çağırarak istemek için GUID özellik sayfasının <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> yöntemi. Bu kayıt defteri girdisi mevcut değilse, kayıt defteri anahtarı düğümü, bir sayfa açıklar.|  
  
### <a name="example"></a>Örnek  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      CSharp\  
        EditorToolsOptions\  
          Formatting\  
            (Default) = reg_sz:#242  
            Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
            General\  
              (Default) = reg_sz:#255  
              Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
              Page      = reg_sz:{3EB2CC0B-033E-4D75-B26A-B2362C25227E}  
            Indentation\  
              (Default) = reg_sz:#250  
              Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
              Page      = reg_sz:{5E21D017-6D2A-4114-A1F1-C923F001CBBB}  
            Newlines\  
              (Default) = reg_sz:#253  
              Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
              Page      = reg_sz:{607D8062-68D1-41E4-9A35-B5E7F14D0481}  
```  
  
## <a name="registry-entries-for-file-name-extension-options"></a>Dosya adı uzantısı seçenekleri için kayıt defteri girişleri  
 Dosya uzantısı için girdi, örneğin ".myext" başında nokta içermesi gerekir.  
  
|Ad|Tür|Aralık|Açıklama|  
|----------|----------|-----------|-----------------|  
|(Varsayılan)|REG_SZ|*GUID*|Bu dosya adı uzantısı türü için varsayılan dil hizmeti için hizmet GUID.|  
  
### <a name="example"></a>Örnek  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    File Extensions\  
      .cpp\  
        (Default) = {B2F072B0-ABC1-11D0-9D62-00C04FD9DFD9}  
```  
  
## <a name="registry-entries-for-editor-options"></a>Düzenleyici seçenekleri için kayıt defteri girişleri  
 *VS Reg kök*\Editors anahtarı, aşağıdaki değerleri içerebilir:  
  
|Ad|Tür|Aralık|Açıklama|  
|----------|----------|-----------|-----------------|  
|(Varsayılan)|REG_SZ|""|Kullanılmayan; adınızı buraya belgeleri için koyabilirsiniz.|  
|DefaultToolboxTab|REG_SZ|""|Düzenleyici etkin olduğunda varsayılan yapmak için araç kutusu sekmesi adı.|  
|Görünen adı|REG_SZ|resID|Görüntülenecek ad **birlikte Aç** iletişim kutusu. Dize kaynak kimliği veya adı standart biçiminde addır.|  
|ExcludeDefTextEditor|REG_DWORD|0-1|İçin kullanılan **birlikte Aç** menü komutu. Belirli bir dosya türü için kullanılabilir düzenleyicileri listesi varsayılan metin düzenleyicide listelemek istemiyorsanız, bu değer 1 olarak ayarlayın.|  
|LinkedEditorGUID|REG_SZ|*\<GUID >*|Bir dosyayı codepage desteğiyle açabilirsiniz hiçbir dil hizmetini kullanılır. Örneğin, açtığınızda .txt dosyası kullanarak **birlikte Aç** komut seçenekleri ile ve kodlamasız kaynak kod düzenleyicisini kullanarak için sağlanır.<br /><br /> Alt adına belirtilen kod sayfası düzenleyici üreteci için GUID'dir; Bu belirli kayıt defteri girdisinde belirtilen bağlı normal Düzenleyici üreteci için GUID'dir. IDE IDE varsayılan Düzenleyicisi'ni kullanarak bir dosya açılmazsa, listede sonraki Düzenleyicisi'ni kullanmayı dener, bu girdi amacı budur. Bu düzenleyici üreteci temelde aynı başarısız Düzenleyici üreteci olduğundan bu sonraki Düzenleyici codepage Düzenleyici üreteci olmamalıdır.|  
|Paket|REG_SZ|*\<GUID >*|Görünen ad ResID için VSPackage GUID.|  
  
### <a name="example"></a>Örnek  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  \Editors\  
    {8281C572-2171-45AA-A642-7D8BC1662F1C}\  
      (Default)            = reg_sz:Html Editor with Encoding  
      DefaultToolboxTab    = reg_sz:HTML  
      DisplayName          = reg_sz:#20101  
      LinkedEditorGUID     = reg_sz:{C76D83F8-A489-11D0-8195-00A0C91BBEE3}  
      Package              = reg_sz:{1B437D20-F8FE-11D2-A6AE-00104BCC7269}  
```  
  
## <a name="registry-entries-for-logical-view-options"></a>Mantıksal görünüm seçenekleri için kayıt defteri girişleri  
 *VS Reg kök*\Editors\\*Düzenleyicisi GUI >*\LogicalViews anahtarı, aşağıdaki değerleri içerebilir.  
  
|Ad|Tür|Aralık|Açıklama|  
|----------|----------|-----------|-----------------|  
|(Varsayılan)|REG_SZ||Kullanılmayan.|  
|*\<GUID >*|REG_SZ|""|Desteklenen mantıksal görünümleri anahtardır. Gereksinim duyduğunuz gibi bu kadar olabilir. Kayıt defteri girdisini önemli, adıdır her zaman boş bir dize değil değeri.|  
  
### <a name="example"></a>Örnek  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  \Editors\  
    {8281C572-2171-45AA-A642-7D8BC1662F1C}\  
      LogicalViews\  
       (Default) = reg_sz:  
       {7651a700-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
       {7651a701-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
       {7651a702-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
       {7651a703-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
```  
  
## <a name="registry-entries-for-editor-extension-options"></a>Kayıt defteri girdilerini Düzenleyicisi uzantısı seçenekleri  
 *VS Reg kök*\Editors\\*Düzenleyicisi GUID*\Extensions anahtarı, aşağıdaki değerleri içerebilir. Dosya adı uzantısı başında nokta içermez.  
  
|Ad|Tür|Aralık|Açıklama|  
|----------|----------|-----------|-----------------|  
|(Varsayılan)|REG_SZ||Kullanılmayan.|  
|*\<ext >*|REG_DWORD|0-0xffffffff|Uzantıları göre önceliğini. İki veya daha fazla dil aynı uzantı paylaşıyorsanız, daha yüksek öncelikli dil seçilir.|  
  
 Ayrıca, bir düzenleyici için geçerli kullanıcının varsayılan seçimi HKEY_Current_User\Software\Microsoft\VisualStudio içinde depolanan\\*X.Y*\Default düzenleyicileri\\*ext*. Seçilen dil hizmeti özel girişi GUID'dir. Bu, geçerli kullanıcı için önceliklidir.  
  
### <a name="example"></a>Örnek  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0\  
  \Editors\  
    {8281C572-2171-45AA-A642-7D8BC1662F1C}\  
      Extensions\  
       (Default) = reg_sz:  
       *         = reg_dword:0x00000018  
       html      = reg_dword:0x00000027  
       shtm      = reg_dword:0x00000027  
       shtml     = reg_dword:0x00000027  
```  
  
## <a name="registry-entries-for-managed-package-framework-language-service-options"></a>Yönetilen paket Framework dil hizmeti seçenekleri için kayıt defteri girişleri  
 Aşağıdaki kayıt defteri girdileri yönetilen paket framework (MPF) dil hizmet sınıfları özgüdür. Bu kayıt defteri girdileri dil hizmeti çeşitli IntelliSense özellikleri için ve diğer gelişmiş düzenleme özellikleri için desteği gösterir.  
  
 Bu kayıt defteri girdileri aracılığıyla erişilen <xref:Microsoft.VisualStudio.Package.LanguagePreferences> sınıfı.  
  
|Ad|Tür|Aralık|Açıklama|  
|----------|----------|-----------|-----------------|  
|CodeSense|REG_DWORD|0-1|IntelliSense işlemleri için destek.|  
|MatchBraces|REG_DWORD|0-1|Eşleşen küme parantezleri, parantezler ve parantezler gibi dil çiftleri desteği.|  
|Quıckınfo|REG_DWORD|0-1|IntelliSense Hızlı bilgileri işlemi için destek.|  
|ShowMatchingBrace|REG_DWORD|0-1|Durum çubuğunda eşleşen dil çifti görüntüleme desteği.|  
|MatchBracesAtCaret|REG_DWORD|0-1|Genellikle iki öğe vurgulama ile eşleşen dil çiftleri görüntüleme desteği.|  
|MaxErrorMessages|REG_DWORD|0-n|Görüntülenebilen hatası sayısı **hata listesi** penceresi.|  
|CodeSenseDelay|REG_DWORD|0-n|IntelliSense işlemi ayrıştırma arka başlatmadan önce gecikme milisaniye sayısı.|  
|EnableAsyncCompletion|REG_DWORD|0-1|Arka plan ayrıştırma desteği.|  
|EnableCommenting|REG_DWORD|0-1|Destek metin seçili bloklarını açıklama eklemek için ve ayrıca uncommenting seçili metin desteği anlamına gelir.|  
|EnableFormatSelection|REG_DWORD|0-1|Otomatik Girinti gibi metin biçimlendirme veya küme ayraçları konumunu ayarlama desteği.|  
|AutoOutlining|REG_DWORD|0-1|Anahat oluşturma (daraltılabilen bölgelerde) desteği.|  
|MaxRegions|REG_DWORD|0-n|Gizli bölgeler dosya başına maksimum sayısı.|  
  
```  
ExampleHKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      XML\  
        (Default)             = reg_sz:{f6819a78-a205-47b5-be1c-675b3c7f0b8e}  
        MatchBraces           = reg_dword:0x00000001  
        QuickInfo             = reg_dword:0x00000001  
        ShowMatchingBrace     = reg_dword:0x00000001  
        MatchBracesAtCaret    = reg_dword:0x00000000  
        MaxErrorMessages      = reg_dword:0x00000064  
        CodeSenseDelay        = reg_dword:0x000001f4  
        MaxRegions            = reg_dword:0x0000000a  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski Dil Hizmeti Geliştirme](../../extensibility/internals/developing-a-legacy-language-service.md)