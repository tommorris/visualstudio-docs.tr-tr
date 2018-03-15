---
title: "Biçim belirticiler hata ayıklayıcı (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- QuickWatch dialog box, format specifiers in C++
- variables [debugger], watch variable symbols
- symbols, watch variable formatting
- QuickWatch dialog box, using format specifiers
- expressions [C++], format specifiers
- specifiers, watch variable format
- specifiers
- Watch window, format specifiers in C++
- watch variable symbols
- format specifiers, debugger
- debugger, format specifiers recognized by
ms.assetid: 0f6f3b7c-ce2c-4b4d-b14f-7589dbed5444
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b7efb90e6f2a2489fffb890c664393252021e6f
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="format-specifiers-in-c-in-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısında C++ içindeki Biçim belirticileri
İçinde bir değer görüntülenir biçimini değiştirebilirsiniz **izleme** penceresi biçim belirticilerini kullanma.  
  
 İçindeki Biçim belirticileri de kullanabilirsiniz **hemen** penceresinde **komutu** penceresi, [tracepoints](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints)ve hatta kaynak windows. Bu windows deyimde üzerinde duraklatma sonucu DataTip içinde görüntülenir. DataTip görüntü biçim belirteci yansıtır.  
  
> [!NOTE]
>  Visual Studio yerel hata ayıklayıcı için yeni bir hata ayıklama motoru değiştirildiğinde, bazı yeni biçim belirticileri eklendi ve bazı eskilerle kaldırıldı. (Karışık yerel ve yönetilen) birlikte çalışabilirliği yaptığınızda eski hata ayıklayıcı hala kullanılan hata ayıklama C + +/ CLI. Bu konudaki aşağıdaki bölümler her hata ayıklama altyapısı için biçim belirticileri gösterir.
>   
>  -   [Biçim belirticiler](#BKMK_Visual_Studio_2012_format_specifiers) yeni hata ayıklama altyapısı içindeki Biçim belirticileri açıklar.  
> -   [Biçim belirticiler birlikte çalışma C + ile hata ayıklama için +/ CLI](#BKMK_Format_specifiers_for_interop_debugging_and_C___edit_and_continue) eski hata ayıklama altyapısı içindeki Biçim belirticileri açıklar.  
  
## <a name="using-format-specifiers"></a>Biçim belirticilerini kullanma  
 Aşağıdaki kodu varsa:  
  
```C++  
int main() {  
    int my_var1 = 0x0065;  
    int my_var2 = 0x0066;  
    int my_var3 = 0x0067;  
}  
```  
  
 Ekleme `my_var1` değişkenini **izleme** penceresi (hata ayıklama, **hata ayıklama > Windows > İzleme > İzleme 1**) ve görüntü onaltılık-ayarlayın (içinde **izlemek**penceresinde, değişkeni sağ tıklatın ve seçin **onaltılı görüntü**). Şimdi Gözcü penceresi 0x0065 değeri içerdiğini gösterir. Bkz. Bu değer Ad sütununda bir tamsayı yerine karakter olarak değişken adını sonra ifade karakter biçim belirticisi eklemek için **c**. **Değeri** sütun artık görünür ile **101 'e'**.  
  
 ![WatchFormatCPlus1](../debugger/media/watchformatcplus1.png "WatchFormatCPlus1")  
  
##  <a name="BKMK_Visual_Studio_2012_format_specifiers"></a> Biçim belirticiler  
 Aşağıdaki tablolarda, Visual Studio'da kullanabileceğiniz biçim belirticileri gösterilmektedir. Kalın yazı tipiyle tanımlayıcıları birlikte çalışma C + ile hata ayıklama için desteklenmez +/ CLI.  
  
|Belirleyici|Biçimi|Özgün izleme değeri|Görüntülenen değeri|  
|---------------|------------|--------------------------|---------------------|  
|d|ondalık tamsayı|0x00000066|102|  
|o|İmzasız sekizlik tamsayı|0x00000066|000000000146|  
|x<br /><br /> **h**|onaltılık tamsayı|102|0xcccccccc|  
|X<br /><br /> **H**|onaltılık tamsayı|102|0xCCCCCCCC|  
|c|tek bir karakter|0x0065, c|101 'e'|  
|s|const char * dizesini|\<Konum > "hello world"|"hello world"|  
|**sb**|const char * dizesini (tırnak işareti)|\<Konum > "hello world"|Merhaba Dünya|  
|s8|UTF-8 dize|\<Konum > "UTF-8 Kahve fincanı â˜• olduğu"|"UTF-8 Kahve fincanı ☕ olduğu"|
|**s8b**|UTF-8 dize (tırnak işareti)|\<Konum > "hello world"|Merhaba Dünya|  
|Su|Unicode (UTF-16 kodlamasını) dizesi|\<Konum > L "hello world"|L "hello world"<br /><br /> U "hello world"|  
|Sub|Unicode (UTF-16 kodlamasını) dizesi (tırnak işareti)|\<Konum > L "hello world"|Merhaba Dünya|  
|bstr|BSTR dizesi|\<Konum > L "hello world"|L "hello world"|  
|env|Ortam öbeği (çift null sonlandırılmış dize)|\<Konum > L "=:: =::\\\\"|L "=:: =::\\\\\\0 = C: = C:\\\\windows\\\\system32\\0ALLUSERSPROFILE =...|
|**s32**|UTF-32 dize|\<Konum > U "hello world"|U "hello world"|  
|**s32b**|UTF-32 dize (tırnak işareti)|\<Konum > U "hello world"|Merhaba Dünya|  
|**tr**|enum|Saturday(6)|Cumartesi|  
|**hv**|İşaretçi türü - Denetlenmekte olan işaretçi değeri, dizi yığın ayırma sonucunu örneğin olduğunu gösterir `new int[3]`.|\<Konum > {\<ilk üye >}|\<Konum > {\<ilk üye >, \<ikinci üye >,...}|  
|**na**|Bir nesne işaretçinin bellek adresi gizler.|\<Konum >, {üye = değer...}|{üye = değer...}|  
|**ND**|Türetilen sınıflar yoksayılıyor yalnızca temel sınıf bilgileri görüntüler|`(Shape*) square` taban sınıfı içerir ve türetilmiş sınıf bilgileri|Görüntüler yalnızca temel sınıf bilgileri|  
|İK|HRESULT veya Win32 hata kodu. (Bu belirleyici bu gibi durumlarda gerekli değil için hata ayıklayıcı şimdi HRESULTs otomatik olarak kodunu çözer.|S_OK|S_OK|  
|wc|Pencere sınıfı bayrağı|0x0010|WC_DEFAULTCHAR|  
|wm|Windows ileti numarası|16|WM_CLOSE|  
|!|RW biçimi, veri türü görünümleri özelleştirmeler yoksayılıyor|\<gösterimi özelleştirilmiş >|4|  
  
> [!NOTE]
>  Zaman **hv** biçim belirticisi varsa, arabellek uzunluğu belirlemek ve öğeleri uygun sayısını görüntülemek hata ayıklayıcı çalışır. Her zaman bir dizi tam arabellek boyutunu bulmak için hata ayıklayıcı mümkün olmadığı için bir boyut belirticisi kullanması gereken `(pBuffer,[bufferSize])` mümkün olduğunda. **Hv** biçim belirteci arabellek boyutu kullanıma hazır olduğu senaryoları için tasarlanmıştır  
  
###  <a name="BKMK_Size_specifiers_for_pointers_as_arrays_in_Visual_Studio_2012"></a> Diziler olarak işaretçileri boyutu tanımlayıcıları  
 Bir dizi olarak görüntülemek istediğiniz bir nesne için bir işaretçi varsa, dizi öğelerinin sayısını belirlemek için bir tamsayı ya da bir deyim kullanabilirsiniz:  
  
|Belirleyici|Biçimi|Özgün izleme değeri|Görüntülenen değeri|  
|---------------|------------|---------------------------|---------------------|  
|n|Ondalık veya **onaltılık** tamsayı|pBuffer,[32]<br /><br /> pBuffer,**[0x20]**|Görüntüler `pBuffer` 32 öğesi dizi olarak.|  
|**[exp]**|Bir tamsayı olarak değerlendirir C++ geçerli bir ifade.|pBuffer, [bufferSize]|Bir dizisi olarak pBuffer görüntüler `bufferSize` öğeleri.|  
|**expand(n)**|Bir tamsayı olarak değerlendirir geçerli bir C++ ifade|pBuffer, expand(2)|Üçüncü öğesine görüntüler  `pBuffer`|  
  
##  <a name="BKMK_Format_specifiers_for_interop_debugging_and_C___edit_and_continue"></a> Biçim belirticiler birlikte çalışma C + ile hata ayıklama için +/ CLI  
 İçindeki belirticileri **kalın** yalnızca yerel ve C + hata ayıklama için desteklenen +/ CLI kod.  
  
|Belirleyici|Biçimi|Özgün izleme değeri|Görüntülenen değeri|  
|---------------|------------|--------------------------|---------------------|  
|**d,i**|imzalanmış ondalık tamsayı|0xF000F065|-268373915|  
|**u**|İmzasız ondalık tamsayı|0x0065|101|  
|o|İmzasız sekizlik tamsayı|0xF065|0170145|  
|x,X|onaltılık tamsayı|61541|0x0000f065|  
|**l,h**|uzun veya kısa önekini: d, i, u, x, o|00406042|0x0c22|  
|**f**|kayan nokta imzalandı|(3./2.), f|1.500000|  
|**e**|İmzalı bilimsel gösterim|(3.0/2.0)|1.500000e+000|  
|**g**|kayan nokta veya bilimsel gösterim imzalı, hangisi daha kısa imzalanır|(3.0/2.0)|1,5|  
|c|tek bir karakter|\<Konum >|101 'e'|  
|s|const char *|\<Konum >|"hello world"|  
|Su|const wchar_t*<br /><br /> const char16_t\*|\<Konum >|L "hello world"|  
|Sub|const wchar_t*<br /><br /> const char16_t\*|\<Konum >|Merhaba Dünya|  
|s8|const char *|\<Konum >|"hello world"|  
|İK|HRESULT veya Win32 hata kodu. (Bu belirleyici bu gibi durumlarda gerekli değil için hata ayıklayıcı şimdi HRESULTs otomatik olarak kodunu çözer.|S_OK|S_OK|  
|wc|Pencere sınıfı bayrağı.|0x00000040,|WC_DEFAULTCHAR|  
|wm|Windows ileti numarası|0x0010|WM_CLOSE|  
|!|RW biçimi, veri türü görünümleri özelleştirmeler yoksayılıyor|\<gösterimi özelleştirilmiş >|4|  
  
###  <a name="BKMK_Format_specifiers_memory_locations_in_interop_debugging_and_C___edit_and_continue"></a> Birlikte çalışma'C + ile hata ayıklama içinde tanımlayıcıları belleğinden biçimlendirmek +/ CLI  
 Aşağıdaki tabloda bellek konumları için kullanılan biçimlendirme simgeler içeriyor. Herhangi bir değer veya bir konuma değerlendirir ifade ile bellek Konum Belirleyicisi kullanabilirsiniz.  
  
|Simgesi|Biçimi|Özgün izleme değeri|Görüntülenen değeri|  
|------------|------------|--------------------------|---------------------|  
|**ma**|64 ASCII karakterleri|0x0012ffac|0x0012ffac .4...0...".0W&.......1W&.0.:W..1...."..1.JO&.1.2.."..1...0y....1|  
|**m**|Onaltılık, 16 bayt ardından tarafından 16 ASCII karakterleri|0x0012ffac|0x0012ffac B3 34 CB 00 84 30 94 80 FF 22 8A 30 57 26 00 00 .4...0...".0W&..|  
|**mb**|Onaltılık, 16 bayt ardından tarafından 16 ASCII karakterleri|0x0012ffac|0x0012ffac B3 34 CB 00 84 30 94 80 FF 22 8A 30 57 26 00 00 .4...0...".0W&..|  
|**mw**|8 sözcükler|0x0012ffac|0x0012ffac 34B3 00CB 3084 8094 22FF 308A 2657 0000|  
|**md**|4 doublewords|0x0012ffac|0x0012ffac 00CB34B3 80943084 308A22FF 00002657|  
|**mq**|2 quadwords|0x0012ffac|0x0012ffac 7ffdf00000000000 5f441a790012fdd4|  
|**mu**|2-bayt karakter (Unicode)|0x0012ffac|0x0012ffac 8478 77f4 ffff ffff 0000 0000 0000 0000|  
  
###  <a name="BKMK_Size_specifier_for_pointers_as_arrays_in_interop_debugging_and_C___edit_and_continue"></a> Birlikte çalışma'C + ile hata ayıklama içindeki diziler olarak işaretçileri boyutu belirleyici +/ CLI  
 Bir dizi olarak görüntülemek istediğiniz bir nesne için bir işaretçi varsa, dizi öğelerinin sayısını belirlemek için bir tamsayı kullanabilirsiniz:  
  
|Belirleyici|Biçimi|İfade|Görüntülenen değeri|  
|---------------|------------|----------------|---------------------|  
|n|ondalık tamsayı|pBuffer [32]|Görüntüler `pBuffer` 32 öğesi dizi olarak.|
