---
title: MSSCCPRJ. SCC dosya | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, MSSCCPRJ.SCC file
- MSSCCPRJ.SCC file
ms.assetid: 6f2e39d6-b79d-407e-976f-b62a3cedd378
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b61478b482ed10aba61ea9ce412dc0fe0725b0bd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="mssccprjscc-file"></a>MSSCCPRJ. SCC dosyası
Visual Studio çözüm ya da proje IDE kullanarak kaynak denetimi altında yerleştirildiğinde, IDE iki temel bilgiler dizeleri formunda eklenti kaynak denetiminden alır. "AuxPath" ve "ProjName" Bu dizeler IDE opak, ancak bunlar eklenti tarafından sürüm denetimindeki proje ve çözüm bulmak için kullanılır. IDE genellikle bu dizeler ilk kez çağırarak edinir [SccGetProjPath](../extensibility/sccgetprojpath-function.md), ve ardından bunları sonraki çağrılar için çözüm ya da proje dosyasında kaydeder [SccOpenProject](../extensibility/sccopenproject-function.md). Bir kullanıcı, çatallarını, dallandırır ya da sürüm denetimindeki çözüm ve proje dosyalarını kopyalar çözüm ve proje dosyalarında yerleşik "AuxPath" ve "ProjName" dizelerini otomatik olarak güncelleştirilmez. Çözüm ve proje dosyalarını doğru konumlarına sürüm denetimindeki işaret ettiğinden emin olmak için kullanıcılar dizeleri el ile güncelleştirmelisiniz. Dizeleri donuk olma amacını taşır olduğundan, bu her zaman nasıl güncelleştirileceği Temizle olmayabilir.  
  
 Kaynak Denetim eklentisi bu sorunu "AuxPath" ve "ProjName" dizeleri MSSCCPRJ adlı özel bir dosyaya depolayarak önleyebilirsiniz. SCC dosyası. Bu, sahibi ve eklenti tarafından tutulan yerel, istemci-tarafı bir dosyadır. Bu dosya kaynak denetiminde hiçbir zaman yerleştirilir ancak kaynak denetimli dosyaları içeren her dizin için eklenti tarafından oluşturulur. Visual Studio çözüm ve proje dosyalarını hangi dosyaların belirlemek için kaynak denetim eklentisi standart ya da kullanıcı tarafından sağlanan listesini karşı dosya uzantılarını karşılaştırabilirsiniz. Bir eklenti MSSCCPRJ desteklediğini IDE algıladıktan sonra. SCC dosyasını, "AuxPath" katıştırmak işlemiyorsa ve çözüm ve proje dosyalarını ve bunu "ProjName" dizeleri MSSCCPRJ Bu dizelerin okur. Bunun yerine SCC dosya.  
  
 MSSCCPRJ destekleyen bir kaynak denetimi eklentisi. SCC dosyası için aşağıdaki yönergelere uyması gerekir:  
  
-   Yalnızca bir MSSCCPRJ olabilir. Her dizin SCC dosyası.  
  
-   Bir MSSCCPRJ. SCC dosyası, belirli bir dizin içinde kaynak denetimi altında birden çok dosya için "AuxPath" ve "ProjName" içerebilir.  
  
-   "AuxPath" dizesi tırnak işaretleri içindeki olmaması gerekir. Sınırlayıcı olarak etrafına tırnak sahip olmasına izin (örneğin, bir çift tırnak boş bir dize belirtmek için kullanılabilir). MSSCCPRJ okurken IDE "AuxPath" dizesi tüm tekliflerden Şerit. SCC dosyası.  
  
-   MSSCCPRJ "ProjName" dizesini. SCC dosya döndürülen dize tam olarak eşleşmelidir `SccGetProjPath` işlevi. İşlev tarafından döndürülen dize çevresinde MSSCCPRJ dizesinde teklifleri varsa. SCC dosyası, tırnak olmalıdır çevresinde ve tersi.  
  
-   Bir MSSCCPRJ. SCC dosya oluşturulduğunda veya bir dosya kaynak denetimi altında yerleştirilir her güncelleştirildiğinde.  
  
-   Eğer MSSCCPRJ bir. SCC dosyası silinir, bir sağlayıcı, bu dizine ilgili bir kaynak denetimi işlemi gerçekleştirir açtığınızda yeniden oluşturmalıdır.  
  
-   Bir MSSCCPRJ. SCC dosya kesinlikle tanımlı biçime uymalıdır.  
  
## <a name="an-illustration-of-the-mssccprjscc-file-format"></a>MSSCCPRJ gösterimi. SCC dosya biçimi  
 Aşağıdaki MSSCCPRJ örneğidir. (Satır numaralarını yalnızca bir kılavuz olarak sağlanır ve dosya gövdesinde eklenmemelidir) SCC dosya biçimi:  
  
 [1. satırına]`SCC = This is a Source Code Control file`  
  
 [Satır 2]  
  
 [Satır 3]`[TestApp.sln]`  
  
 [Satır 4]`SCC_Aux_Path = "\\server\vss\"`  
  
 [Satır 5]`SCC_Project_Name = "$/TestApp"`  
  
 [Satır 6]  
  
 [Satır 7]`[TestApp.csproj]`  
  
 [Satır 8]`SCC_Aux_Path = "\\server\vss\"`  
  
 [Satır 9]`SCC_Project_Name = "$/TestApp"`  
  
 İlk satırı dosyasının amacı durumları ve bu türdeki tüm dosyaları için imza görevi görür. Bu satır, tam olarak bu tüm MSSCCPRJ gibi görünmelidir. SCC dosyalar:  
  
 `SCC = This is a Source Code Control file`  
  
 Aşağıda bir dosya adı köşeli ayraçlar içinde tarafından işaretlenen her bir dosya için ayarları bölümüdür. Bu bölümde, izlenen her dosya için tekrarlanır. Bu satır, bir dosya adı öğesine, örneğidir `[TestApp.csproj]`. IDE aşağıdaki iki satırı bekliyor. Bu ancak tanımlanan değerlerden birisini stili tanımlamaz. Değişkenleri `SCC_Aux_Path` ve `SCC_Project_Name`.  
  
 `SCC_Aux_Path = "\\server\vss\"`  
  
 `SCC_Project_Name = "$/TestApp"`  
  
 Bu bölüm için son sınırlayıcı yoktur. Dosyasında bulunan tüm değişmez değerleri yanı sıra, dosyanın adını scc.h üstbilgi dosyasında tanımlanmıştır. Daha fazla bilgi için bkz: [dizeleri kullanılan bir kaynak denetimi eklentisi bulmak için anahtar olarak](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim Eklentileri](../extensibility/source-control-plug-ins.md)   
 [Kaynak denetimi eklenti bulmak için anahtar olarak kullanılan dizeleri](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md)