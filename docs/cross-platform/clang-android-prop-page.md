---
title: Clang proje özellikleri (Android C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/23/2017
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 663140ea-a568-472b-a79a-dfea8818e06a
author: corob
ms.author: mblome
manager: douge
f1_keywords:
- VC.Project.VCClangCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCClangCompilerTool.DebugInformationFormat
- VC.Project.VCClangCompilerTool.ObjectFile
- VC.Project.VCClangCompilerTool.WarningLevel
- VC.Project.VCClangCompilerTool.WarnAsError
- VC.Project.VCClangCompilerTool.Verbose
- VC.Project.VCClangCompilerTool.Optimization
- VC.Project.VCClangCompilerTool.StrictAliasing
- VC.Project.VCClangCompilerTool.OmitFramePointers
- VC.Project.VCClangCompilerTool.ExceptionHandling
- VC.Project.VCClangCompilerTool.EnableFunctionLevelLinking
- VC.Project.VCClangCompilerTool.DataLevelLinking
- VC.Project.VCClangCompilerTool.DataLevelLinking
- VC.Project.VCClangCompilerTool.FloatABI
- VC.Project.VCClangCompilerTool.BufferSecurityCheck
- VC.Project.VCClangCompilerTool.PIC
- VC.Project.VCClangCompilerTool.UseShortEnums
- VC.Project.VCClangCompilerTool.RuntimeTypeInfo
- VC.Project.VCClangCompilerTool.CLanguageStandard
- VC.Project.VCClangCompilerTool.CppLanguageStandard
- VC.Project.VCClangCompilerTool.PreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefineAllPreprocessorDefinitions
- VC.Project.VCClangCompilerTool.ShowIncludes
- VC.Project.VCClangCompilerTool.PrecompiledHeader
- VC.Project.VCClangCompilerTool.PrecompiledHeaderFile
- VC.Project.VCClangCompilerTool.PrecompiledHeaderOutputFileDirectory
- VC.Project.VCClangCompilerTool.PrecompiledHeaderCompileAs
- VC.Project.VCClangCompilerTool.CompileAs
- VC.Project.VCClangCompilerTool.ForcedIncludeFiles
- VC.Project.VCClangCompilerTool.MultiProcessorCompilation
- vc.project.AdditionalOptionsPage
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 8a1fd92a41f145e097615bea4434ea80fd592416
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31067538"
---
# <a name="clang-project-properties-android-c"></a>Clang proje özellikleri (Android C++)

Özellik | Açıklama | Seçenekler
--- | ---| ---
Ek içeren dizinler | INCLUDE yolu eklemek için bir veya daha fazla dizinleri belirtir; birden fazla ise noktalı virgülle ayırın. (-I[path]).
Hata ayıklama bilgileri biçimi | Derleyici tarafından üretilen hata ayıklama bilgi türünü belirtir. | **Hiçbiri** -derleme daha hızlı şekilde hiçbir hata ayıklama bilgilerini oluşturur.<br>**Tam hata ayıklama bilgileri (DWARF2)** -oluşturmak DWARF2 hata ayıklama bilgileri.<br>**Satır numarası bilgilerini** -yalnızca satır numarası oluşturmak bilgi.<br>
Nesne dosya adı | Varsayılan nesne dosya adı geçersiz kılmak için bir ad belirtir; Dosya veya dizin adı olabilir. (/ Fo[name]).
Uyarı düzeyi | Nasıl katı hakkında kod hata olarak derleyici istediğinizi belirtin.  Diğer bayraklar doğrudan ek seçenekler eklenmesi gerekir. (/ w, /Weverything). | **Tüm uyarıları devre dışı bırakma** -tüm Derleyici uyarılarını devre dışı bırakır.<br>**EnableAllWarnings** -varsayılan olarak devre dışı dahil olmak üzere tüm uyarıları sağlar.<br>
Uyarıları hata ele | Tüm derleyici uyarıları hata olarak değerlendirir. Yeni bir proje için /WX tüm derlemeleri kullanmak en iyi yöntem olabilir; Tüm uyarıları çözümleme, en az olası Bul sabit kod kusurları güvence altına alır.
Ayrıntılı modunu etkinleştir | Ayrıntılı çıktı çalıştırabilir ve komutları göster.
En iyi duruma getirme | Uygulama için en iyi duruma getirme düzeyini belirtir. | **Özel** -özel en iyi duruma getirme.<br>**Devre dışı** -iyileştirme devre dışı bırakın.<br>**Boyutu en aza** -boyutu için en iyi duruma getirme.<br>**Hızı en üst düzeye** -hızı için en iyi duruma getirme.<br>**Tam iyileştirme** -pahalı iyileştirmeler.<br>
Katı yumuşatma | Sıkı diğer ad kuralları varsayalım.  Bir türdeki bir nesne hiçbir zaman farklı türde bir nesne ile aynı adresinde bulunan olduğu kabul edilir.
Çerçeve işaretçisini atlama | Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.
C++ özel durumlarını etkinleştirin | Özel durum derleyici tarafından kullanılacak işleme modelini belirtir. | **Hayır** -özel durum işleme devre dışı bırakın.<br>**Evet** -özel durum işleme etkinleştirin.<br>**Tablo bırakma** - gerekli tüm statik verileri oluşturur, ancak oluşturulan kodu etkilemez.<br>
İşlev düzeyi bağlamayı etkinleştir | Paketlenmiş işlevler (COMDATs) biçiminde paket tekil işlevler için derleyicisi tanır. Düzenleme için gerekli ve çalışmaya devam eder.     (ffunction-bölümler).
Veri düzeyi bağlamayı etkinleştir | Her bir veri öğesi ayrı bir bölüm yayma tarafından kullanılmayan verileri kaldırmak bağlayıcı iyileştirmeler sağlar.
Gelişmiş SIMD(Neon) etkinleştir | Kayan nokta donanımı NEON için kod oluşturmayı etkinleştirir. Bu, yalnızca arm mimarisi için geçerlidir.
Kayan nokta ABI | Kayan nokta ABI seçmek için seçim seçeneği'ni kullanın. | **Yazılım** -'Geçici' neden içeren kitaplık çağırır kayan nokta işlemlerinde çıktı üretmek derleyici.<br>**SoftFP** - 'SoftFP' donanım kayan nokta yönergeleri kullanarak kod oluşturma sağlar, ancak hala yumuşak float çağırma kurallarını kullanır.<br>**Sabit** -kayan nokta yönergeleri ve kullandığı FPU özgü çağırma kurallarını 'Sabit' alows oluşturma.<br>
Güvenlik denetimi | Güvenlik denetimi yığını arabellek fazla çalıştığında, ortak denenen saldırısını bir programın güvenlik bağlı algılanmasına yardımcı olur. (fstack-koruyucu). | **Güvenlik denetimi devre dışı** -güvenlik denetimi devre dışı bırakın.<br>**Güvenlik denetimi etkinleştir** -güvenlik denetimini etkinleştir. (koruyucu fstack)<br>
Konum bağımsız kodu | Paylaşılan bir kitaplık kullanmak için konum bağımsız kod (PIC) oluşturur.
Kısa numaralandırmaları kullanın | Enum türü kullanan yalnızca giriş olası değerler kümesi tarafından gereken sayıda bayt.
Çalışma zamanı türü bilgileri etkinleştir | Çalışma zamanında (çalışma zamanı türü bilgileri) C++ nesne türlerini denetlemek için kod ekler.     (frtti, fno rttı)
C dili standart | C dili standart belirler. | **Default**<br>**C89** -C89 dil standardı.<br>**C99** -C99 dil standardı.<br>**C11** -C11 dil standardı.<br>**C99 (GNU Dialect)** -C99 (GNU Dialect) dil standardı.<br>**C11 (GNU Dialect)** -C11 (GNU Dialect) dil standardı.<br>
C++ dili standart | C++ dili standart belirler. | **Default**<br>**C ++ 03** -C ++ 03 dil standardı.<br>**C ++ 11** -C ++ 11 dil standardı.<br>**C ++ 14** -C ++ 14 dil standardı.<br>**C ++ 03 (GNU Dialect)** - C ++ 03 (GNU Dialect) dil standardı.<br>**C ++ 11 (GNU Dialect)** - C ++ 11 (GNU Dialect) dil standardı.<br>**C ++ 14 (GNU Dialect)** - C ++ 14 (GNU Dialect) dil standardı.<br>
Önişlemci tanımları | Kaynak dosyanızı önişlem simgelerini tanımlar. (-D)
Önişlemci tanımları tanımlarını Kaldır | Bir veya daha fazla önişlemci undefines belirtir.  (-U [makrosu])
Tüm önişlemci tanımları tanımlarını Kaldır | Önceden tanımlanmış tüm önişlemci değerleri tanımsız.  (-undef)
Göster içerir | Derleyici çıktı ile INCLUDE dosyaların bir listesini oluşturur.  (-H)
Önceden derlenmiş üst bilgi | Oluşturma/kullanım önceden derlenmiş üstbilgi: etkinleştirir veya derleme sırasında önceden derlenmiş üstbilgi kullanımını. | **Kullanım** -önceden derlenmiş üst bilgi kullanın.<br>**Önceden derlenmiş üstbilgiler kullanılmıyor** -önceden derlenmiş üstbilgi kullanmayan.<br>
Önceden derlenmiş üstbilgi dosyası | Önceden derlenmiş üst bilgi dosyası için kullanılacak üstbilgi dosyası adı belirtir. Bu dosya ayrıca 'Zorla dahil dosyalara' derleme sırasında eklenecek
Önceden derlenmiş üst bilgi çıktı dosyası dizini | Oluşturulan önceden derlenmiş üst bilgi dizinini belirtir. Bu dizin de 'Ek içeren dizinler için' derleme sırasında eklenir
Önceden derlenmiş üst bilgi olarak derleme | Select derleme dil seçeneği önceden derlenmiş üst bilgi dosyası için (- x c-başlık - x c ++ - başlık). | **C kodu olarak derleme** -C kodu olarak derleyin.<br>**C++ kodu olarak derleme** -C++ kodu olarak derleyin.<br>
Olarak derleme | .C ve .cpp dosyaları için derleme dil seçeneği seçin.  'Default' temel alınarak .c veya .cpp uzantı algılar. (-x c, -x c++) | **Varsayılan** -varsayılan.<br>**C kodu olarak derleme** -C kodu olarak derleyin.<br>**C++ kodu olarak derleme** -C++ kodu olarak derleyin.<br>
Zorlanan dosyaları dahil etme | bir veya daha fazla zorunlu dosyaları içerir.     (-[name] dahil)
Birden çok işlemcili derleme | Birden çok işlemcili derleme.
Ek Seçenekler | Ek Seçenekler.
