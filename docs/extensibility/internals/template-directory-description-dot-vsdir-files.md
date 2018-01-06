---
title: "Şablon dizin açıklaması (. Vsdir) dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .vsdir files
- VSDIR files
- template directory description files
ms.assetid: 9df51800-190e-4662-b685-fdaafcff1400
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 739dd0d41fb63c4993dad0d66737aaada1cf01c4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="template-directory-description-vsdir-files"></a>Şablon dizin açıklaması (. Vsdir) dosyaları
Bir şablon dizin tanımı dosyası (.vsdir) tümleşik geliştirme ortamı (IDE) klasörler, sihirbaz .vsz dosyaları ve iletişim kutuları projenizde ile ilişkili şablon dosyalarını görüntülemek için sağlayan bir metin dosyasıdır. İçeriği, dosya veya klasör her bir kayıt içerir. Yalnızca bir .vsdir dosyası genellikle birden çok klasörler, sihirbaz veya şablon dosyalarını açıklamak için sağlanan olsa da, tüm .vsdir dosyalarını başvurulan bir konumda birleştirilir.  
  
 Klasörleri (alt) .vsdir dosya ve .vsdir dosyasında başvurulan dosyaların tümü aynı dizinde bulunur. IDE ne zaman bir Sihirbazı'nı çalıştıran veya bir klasör veya dosyada görüntüler **yeni proje** veya **Yeni Öğe Ekle** iletişim kutuları, IDE inceler .vsdir dosyanın olup olmadığını belirlemek için yürütülen dosyaları içeren dizini mevcut. .Vsdir dosya bulunursa, IDE yürütülen veya görüntülenen klasör veya dosya için bir giriş içerip içermediğini belirlemek için okur. Bir giriş bulunursa, IDE Sihirbazı'nın yürütme veya içeriği görüntüleme bilgileri kullanır.  
  
 Aşağıdaki kod örneğinde SourceFiles.vsdir dosyasındadır içinde \<EnvSDK > \BscPrj\BscPrj\BscPrjProjectItems\Source_Files kayıt defteri anahtarı:  
  
```  
HeaderFile.h|{E59935A1-6156-11d1-87A6-00A0C91E2A46}|#125|130|#126|0|0|0|#127  
SourceFile.cpp|{E59935A1-6156-11d1-87A6-00A0C91E2A46}|#122|110|#123|0|0|0|#124  
```  
  
 Bu durumda, iki tek dosyada kayıtlarıdır. Yeni bir satır (satır başı karakteri), her kayıt ayırır. Her satır, farklı bir dosya türü temsil eder. Bir kanal (&#124;) karakter her bir kayıttaki alan ayırır. Tek bir dizin farklı dosya adlarına sahip birden çok .vsdir dosyaları içerebilir veya her dosya türü için bir .vsdir dosyası sağlayabilirsiniz.  
  
## <a name="fields"></a>Alanlar  
 Aşağıdaki tablo her kayıt için belirtilen alanları listeler.  
  
|Alan|Açıklama|  
|-----------|-----------------|  
|Göreli yol adını (RelPathName)|HeaderFile.h veya MyWizard.vsz gibi klasör, şablonu veya .vsz dosyasının adıdır. Bu alan, bir klasör temsil etmek için kullanılan bir adı da olabilir.|  
|{clsidPackage}|Yerelleştirilmiş dizeleri, LocalizedName, açıklama, IconResourceId ve SuggestedBaseName, gibi VSPackage'nın uydu dinamik bağlantı kitaplığı (DLL) kaynaklarında erişimini etkinleştirir VSPackage GUID. Yapmasý sağlanmıyorsa IconResourceId geçerlidir. **Not:** bir veya daha önceki alanlarının kaynak tanımlayıcısı olmadığı sürece bu alan isteğe bağlıdır. Bu alan genellikle kendi metin yerelleştirme değil üçüncü taraf Sihirbazlarla karşılık gelen .vsdir dosyaları için boştur.|  
|LocalizedName|Şablon dosyası veya Sihirbazı'nı yerelleştirilmiş adı. Bu alan bir dize veya bir kaynak tanımlayıcısı "#ResID" biçiminde olabilir. Bu ad **Yeni Öğe Ekle** iletişim kutusu. **Not:** LocalizedName bir kaynak tanımlayıcısıdır sonra {clsidPackage} gereklidir.|  
|SortPriority|Bu şablon dosyası ya da Sihirbazı göre önceliğini temsil eden bir tamsayı. Bu öğe 1 değeri varsa, örneğin, ardından bu öğeyi bir değere sahip diğer öğeleri 1 ve 2 veya daha büyük bir sıralama değeri olan tüm öğeleri öncesinde yanındaki görüntülenir.<br /><br /> Aynı dizinde öğeleri sıralama önceliğini görelidir. Aynı dizinde birden fazla .vsdir dosyası olabilir. Bu durumda, tüm öğeleri *.* dizindeki dosyaların vsdir birleştirilir. Öğeler aynı önceliğe sahip büyük küçük harf duyarsız lexicographic görüntülenen ad sırayla listelenir. `_wcsicmp` İşlevi öğeleri sipariş için kullanılır.<br /><br /> .Vsdir dosyalarında açıklanmayan öğeleri .vsdir dosyalarında listelenen en yüksek öncelik sayısından büyük bir öncelik numarası içerir. Bu öğeler adlarının bağımsız olarak görüntülenen listesinin sonunda olduğunu sonucudur.|  
|Açıklama|Şablon dosyası ya da Sihirbazı yerelleştirilmiş açıklaması. Bu alan bir dize veya bir kaynak tanımlayıcısı "#ResID" biçiminde olabilir. Bu dize görünür **yeni proje** veya **Yeni Öğe Ekle** öğe seçildiğinde iletişim kutusu.|  
|Yapmasý veya {clsidPackage}|Şablon dosyası ya da Sihirbazı için bir simge yüklemek için kullanılır. Simge IconResourceId kullanarak bir .dll veya .exe dosyasının dışında bir kaynak olarak yüklenir. Bu .dll veya .exe dosyasının tam yolunu kullanarak veya bir VSPackage GUİD'si kullanarak tanımlanabilir. Uygulama VSPackage DLL simgesini (değil DLL uydu) yüklemek için kullanılır.|  
|IconResourceId|DLL ya da VSPackage uygulamasında görüntülemek için bu simgeyi belirler DLL kaynak tanımlayıcısı.|  
|Bayrakları (<xref:Microsoft.VisualStudio.Shell.Interop.__VSDIRFLAGS>)|Devre dışı bırakmak veya etkinleştirmek için kullanılan **adı** ve **konumu** üzerinde alanları **Yeni Öğe Ekle** iletişim kutusu. Değeri **bayrakları** alan gerekli bit bayrakları bileşimi ondalık aynıdır.<br /><br /> Bir kullanıcı seçtiğinde bir öğe üzerinde **yeni** sekmesi, proje belirler ad alanını ve konum alanı ne zaman gösterilip gösterilmeyeceğini **Yeni Öğe Ekle** iletişim kutusu ilk kez görüntülenir. Bir öğe, öğe seçildiğinde alanları devre dışı karşı etkinleştirilip etkinleştirilmediğini .vsdir dosyası aracılığıyla bir yalnızca kontrol edebilirsiniz.|  
|SuggestedBaseName|Dosya, sihirbaz veya şablon için varsayılan adını temsil eder. Bu alan bir dize veya bir kaynak tanımlayıcısı "#ResID" biçiminde olur. IDE öğesi için bir varsayılan ad sağlamak için bu değeri kullanır. Bu taban değer adı MyFile21.asp gibi benzersiz hale getirmek amacıyla bir tamsayı değeri olan eklenir.<br /><br /> Önceki listede yapmasý, IconResourceId, bayrakları, açıklama ve SuggestedBaseNumber yalnızca şablonu ve Sihirbazı dosyaları için geçerli. Bu alanların klasörler için geçerli değildir. Bu olgu BscPrjProjectItems dosyasında kodda gösterildiği \<EnvSDK > \BscPrj\BscPrj\BscPrjProjectItems kayıt defteri anahtarı. Bu dosya üç kayıtlarıyla (her klasör için bir tane) her kayıt için dört alanlar içeriyor: RelPathName, {clsidPackage} LocalizedName ve SortPriority.<br /><br /> `General&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#110&#124;100`<br /><br /> `Source_Files&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#111&#124;110`<br /><br /> `Env&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#112&#124;120`|  
  
 Sihirbaz dosyası oluşturduğunuzda, aşağıdaki sorunları de dikkate almalısınız.  
  
-   Kendisi için anlamlı veri yok herhangi bir gerekli olmayan alan yer tutucu olarak 0 (sıfır) içermelidir.  
  
-   Yerelleştirilmiş ad sağlanırsa, göreli yol adı Sihirbazı dosyasında kullanılır.  
  
-   Yapmasý clsidPackage simgesi konumu için geçersiz kılar.  
  
-   Hiçbir simge tanımlanmışsa, bu uzantıya sahip bir dosya için varsayılan simge IDE değiştirir.  
  
-   Önerilen temel ad sağlanırsa, 'Projesindeki' kullanılır.  
  
-   .Vsz dosyaları, klasörleri veya şablon dosyalarını silerseniz, ilişkili kayıtlarını .vsdir dosyasından de kaldırmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sihirbazlar](../../extensibility/internals/wizards.md)   
 [Sihirbaz (.Vsz) Dosyası](../../extensibility/internals/wizard-dot-vsz-file.md)