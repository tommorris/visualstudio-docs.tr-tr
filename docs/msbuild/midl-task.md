---
title: MIDL görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- VC.Project.VCMidlTool.ServerStubFile
- VC.Project.VCMidlTool.ApplicationConfigurationMode
- VC.Project.VCMidlTool.GenerateServerFiles
- VC.Project.VCMidlTool.ClientStubFile
- VC.Project.VCMidlTool.LocaleID
- VC.Project.VCMidlTool.GenerateClientFiles
- VC.Project.VCMidlTool.SuppressCompilerWarnings
- VC.Project.VCMidlTool.TypeLibFormat
- vc.task.midl
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild (Visual C++), MIDL task
- MIDL task (MSBuild (Visual C++))
ms.assetid: 727efa8c-3336-40b8-8bef-ae6cbd77a422
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b46e4dc771ad5bb95185647a4769359427886f24
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="midl-task"></a>MIDL Görevi
Microsoft arabirimi tanım dili (MIDL) derleyici aracı sarmalar midl.exe. Daha fazla bilgi için "MIDL komut satırı başvurusu" bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **MIDL** görev. Çoğu görevi parametreleri ve parametreleri, birkaç kümelerini bir komut satırı seçeneğine karşılık gelir.  
  
-   **AdditionalIncludeDirectories**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Bir dizine alınan IDL dosyaları, dahil edilen üstbilgi dosyaları ve uygulama yapılandırma dosyaları (ACF) arama dizinlerinin listesi ekler.  
  
     Daha fazla bilgi için bkz: **/I** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **AdditionalOptions**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Komut satırı seçeneklerinin listesi. Örneğin, **"***/seçenek 1 /option2 /option#*". Tüm diğer MIDL görevi parametresi tarafından temsil edilmeyen komut satırı seçeneklerini belirtmek için bu parametreyi kullanın.  
  
     Daha fazla bilgi için "MIDL komut satırı başvurusu" bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **ApplicationConfigurationMode**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, bazı ACF anahtar sözcükleri IDL dosyasında kullanmanıza olanak sağlar.  
  
     Daha fazla bilgi için bkz: **/app_config** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **ClientStubFile**  
  
     İsteğe bağlı **dize** parametresi.  
  
     RPC arabirimi için istemci saplama dosyası adını belirtir.  
  
     Daha fazla bilgi için bkz: **/cstub** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi. Ayrıca bkz. **ServerStubFile** bu tabloda parametresi.  
  
-   **CPreprocessOptions**  
  
     İsteğe bağlı **dize** parametresi.  
  
     C/C++ ön işlemci geçirmek için seçeneklerini belirtir. Önişlemci seçenekleri boşlukla ayrılmış bir listesini belirtin.  
  
     Daha fazla bilgi için bkz: **/cpp_opt** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **DefaultCharType**  
  
     İsteğe bağlı **dize** parametresi.  
  
     C derleyicisi oluşturulan kodu derlemek için kullanacağı varsayılan karakter türü belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    |Değer|Komut satırı seçeneği|  
    |-----------|--------------------------|  
    |**İmzalı**|**/char imzalı**|  
    |**İmzasız**|**/char imzalanmamış**|  
    |**Ascii**|**/char ascii7**|  
  
     Daha fazla bilgi için bkz: **/char** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **DllDataFileName**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Oluşturulan dosya adını belirtir *dlldata* proxy DLL dosyası.  
  
     Daha fazla bilgi için bkz: **/dlldata** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **EnableErrorChecks**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Çalışma zamanında oluşturulan saplamalar gerçekleştirecek denetlenirken hata türünü belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    |Değer|Komut satırı seçeneği|  
    |-----------|--------------------------|  
    |**Yok**|**/Error yok**|  
    |**EnableCustom**|**/Error**|  
    |**Tüm**|**Tüm /Error**|  
  
     Daha fazla bilgi için bkz: **/error** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **ErrorCheckAllocations**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, bellek yetersiz hataları kontrol edin.  
  
     Daha fazla bilgi için bkz: **/error ayırma** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **ErrorCheckBounds**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`uyumluluğunu değişen boyutunu denetler ve iletim uzunluğu belirtimi karşı diziler değişen.  
  
     Daha fazla bilgi için bkz: **/error bounds_check** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **ErrorCheckEnumRange**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, numaralandırma değerlerinin bir izin verilen aralıktaki olduğunu denetler.  
  
     Daha fazla bilgi için bkz: **/error enum** seçeneği komut satırı Yardımı'ndaki (**/?**) midl.exe için.  
  
-   **ErrorCheckRefPointers**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, null başvuru işaretçileri istemci saplamalar geçirilir denetleyin.  
  
     Daha fazla bilgi için bkz: **/error ref** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **ErrorCheckStubData**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, sunucu tarafında unmarshaling özel durumları yakalar ve istemciye yayar bir saplama oluşturur.  
  
     Daha fazla bilgi için bkz: **/error stub_data** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **GenerateClientFiles**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Derleyici bir RPC arabirimi için istemci tarafı C kaynak dosyaları oluşturup oluşturmayacağını belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    |Değer|Komut satırı seçeneği|  
    |-----------|--------------------------|  
    |**Yok**|**/Client yok**|  
    |**Stub**|**/Client saplama**|  
  
     Daha fazla bilgi için bkz: **/client** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **GenerateServerFiles**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Derleyici bir RPC arabirimi için sunucu tarafı C kaynak dosyaları oluşturup oluşturmayacağını belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    |Değer|Komut satırı seçeneği|  
    |-----------|--------------------------|  
    |**Yok**|**/ Server yok**|  
    |**Stub**|**/ Server saplama**|  
  
     Daha fazla bilgi için bkz: **/Server** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **GenerateStublessProxies**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, tam olarak yorumlanan saplamalar nesnesi arabirimleri stubless proxy'leri birlikte oluşturur.  
  
     Daha fazla bilgi için bkz: **/Oicf** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **GenerateTypeLibrary**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, bir tür kitaplığı (.tlb) dosyası değil oluşturulur.  
  
     Daha fazla bilgi için bkz: **/notlb** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **HeaderFileName**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Oluşturulan üstbilgi dosyası adını belirtir.  
  
     Daha fazla bilgi için bkz: **/h** veya **/header** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **IgnoreStandardIncludePath**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, yalnızca kullanılarak belirtilen dizinleri MIDL görevi arar **AdditionalIncludeDirectories** geçin ve geçerli dizinde ve INCLUDE ortam değişkeni tarafından belirtilen dizin yok sayar.  
  
     Daha fazla bilgi için bkz: **/no_def_idir** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **InterfaceIdentifierFileName**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Adını belirtir. *arabirim tanımlayıcısı dosyası* COM arabirimi için. Bu, IDL dosya adına "_i.c" ekleyerek elde varsayılan adı geçersiz kılar.  
  
     Daha fazla bilgi için bkz: **/iid** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **LocaleID**  
  
     İsteğe bağlı **int** parametresi.  
  
     Belirtir *yerel ayar tanımlayıcısı* giriş dosyaları, dosya adlarını ve dizin yolları uluslararası karakterlerin kullanımını sağlar. Bir ondalık yerel ayar tanımlayıcısı belirtin.  
  
     Daha fazla bilgi için bkz: **/lcid** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi. Ayrıca "Yerel ayar kimlikleri atanan tarafından Microsoft'taki" MSDN bakın.  
  
-   **MkTypLibCompatible**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, 2.03 mktyplib.exe sürümü ile uyumlu olacak şekilde giriş dosyasının biçimi gerektirir.  
  
     Daha fazla bilgi için bkz: **/mktyplib203** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi. Ayrıca, "ODL dosyası sözdizimi" MSDN Web sitesinde bkz.  
  
-   **OutputDirectory**  
  
     İsteğe bağlı **dize** parametresi.  
  
     MIDL görevi çıktı dosyalarını nereye yazdığını varsayılan dizini belirtir.  
  
     Daha fazla bilgi için bkz: **/out** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **PreprocessorDefinitions**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Bir veya daha fazla belirtir *tanımlar*; diğer bir deyişle, bir ad ve isteğe bağlı değeri C önişlemci geçirilmesi IF bir `#define` yönergesi. Her tanımlama biçimidir, *[= değer] adı*.  
  
     Daha fazla bilgi için bkz: **/D** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi. Ayrıca bkz **UndefinePreprocessorDefinitions** bu tabloda parametresi.  
  
-   **ProxyFileName**  
  
     İsteğe bağlı **dize** parametresi.  
  
     COM arabirimi için arabirim proxy dosyasının adını belirtir.  
  
     Daha fazla bilgi için bkz: **/proxy** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **RedirectOutputAndErrors**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Hata iletileri ve uyarılar, belirtilen dosyaya standart çıktısından gibi çıkış yeniden yönlendirir.  
  
     Daha fazla bilgi için bkz: **/o** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **ServerStubFile**  
  
     İsteğe bağlı **dize** parametresi.  
  
     RPC arabirimi sunucu saplama dosya adını belirtir.  
  
     Daha fazla bilgi için bkz: **/sstub** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi. Ayrıca bkz **ClientStubFile** bu tabloda parametresi.  
  
-   **Kaynak**  
  
     Gerekli `ITaskItem[]` parametresi.  
  
     Kaynak dosyaları boşluklarla ayrılmış listesini belirtir.  
  
-   **StructMemberAlignment**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Hizalamasını belirtir (*düzeyi sevk*) hedef sistemdeki yapıların.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    |Değer|Komut satırı seçeneği|  
    |-----------|--------------------------|  
    |**NotSet**|*\<yok >*|  
    |**1**|**/Zp1**|  
    |**2**|**/Zp2**|  
    |**4**|**/Zp4**|  
    |**8**|**/Zp8**|  
  
     Daha fazla bilgi için bkz: **/Zp** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi. **/Zp** seçenektir eşdeğer **Pack** seçeneği ve eski **/ Hizala** seçeneği.  
  
-   **SuppressCompilerWarnings**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, MIDL görevi uyarı iletileri gizler.  
  
     Daha fazla bilgi için bkz: **/no_warn** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **SuppressStartupBanner**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisini görüntülenmesini engeller.  
  
     Daha fazla bilgi için bkz: **/nologo** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **TargetEnvironment**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Uygulamanın çalıştığı ortam belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    |Değer|Komut satırı seçeneği|  
    |-----------|--------------------------|  
    |**NotSet**|*\<yok >*|  
    |**Win32**|**win32/Env**|  
    |**Itanium**|**/ env IA64**|  
    |**X64**|**/env x64**|  
  
     Daha fazla bilgi için bkz: **/env** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **TrackerLogDirectory**  
  
     İsteğe bağlı `String` parametresi.  
  
     Bu görev için izleme günlüklerinin depolandığı Ara dizini belirtir.  
  
-   **TypeLibFormat**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Tür kitaplığı dosyasının biçimini belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    |Değer|Komut satırı seçeneği|  
    |-----------|--------------------------|  
    |**NewFormat**|**/newtlb**|  
    |**OldFormat**|**/oldtlb**|  
  
     Daha fazla bilgi için bkz: **/newtlb** ve **/oldtlb** Seçenekleri "MIDL komut satırı başvurusu" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **TypeLibraryName**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Tür kitaplığı dosya adını belirtir.  
  
     Daha fazla bilgi için bkz: **TLB** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **UndefinePreprocessorDefinitions**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Önceki herhangi bir ad tanımını adı C önişlemci geçirerek kaldırır IF bir `#undefine` yönergesi. Bir veya daha fazla önceden tanımlanmış adlarını belirtin.  
  
     Daha fazla bilgi için bkz: **/U** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi. Ayrıca bkz **PreprocessorDefinitions** bu tabloda parametresi.  
  
-   **ValidateAllParameters**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, çalışma zamanında bütünleştirme denetimleri gerçekleştirmek için kullanılan ek hata denetimi bilgilerini oluşturur. Varsa `false`, hata denetimi bilgiler değil oluşturulur.  
  
     Daha fazla bilgi için bkz: **/ sağlam** ve **/no_robust** Seçenekleri "MIDL komut satırı başvurusu" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **WarnAsError**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, tüm uyarıları hata olarak kabul eder.  
  
     Varsa **WarningLevel** MIDL görevi parametresi belirtilmezse, varsayılan düzeyde düzey 1 uyarıları hata olarak kabul edilir.  
  
     Daha fazla bilgi için bkz: **/WX** Seçenekleri "MIDL komut satırı başvurusu" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi. Ayrıca bkz **WarningLevel** bu tabloda parametresi.  
  
-   **WarningLevel**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Önem derecesi belirtir (*uyarı düzeyi*) yaymak üzere uyarılar. Herhangi bir uyarı için 0 değerini yayınlanır. Uyarı düzeyi sayısal ise bir uyarı Aksi halde, gösterilen belirtilen değere eşit veya daha az.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    |Değer|Komut satırı seçeneği|  
    |-----------|--------------------------|  
    |**0**|**/ W0**|  
    |**1**|**/ W1**|  
    |**2**|**/ W2**|  
    |**3**|**/ W3**|  
    |**4**|**/ W4**|  
  
     Daha fazla bilgi için bkz: **/W** "MIDL komut satırı başvurusu" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi. Ayrıca bkz **WarnAsError** bu tabloda parametresi.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)