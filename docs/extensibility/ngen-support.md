---
title: "VSIX v3 Ngen desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1472e884-c74e-4c23-9d4a-6d8bdcac043b
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 433ff9555ce4a3e896aca1143ee649217f80dc7f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ngen-support-in-vsix-v3"></a>VSIX v3 Ngen desteği

(Sürüm 3) uzantısı Visual Studio 2017 ve yeni VSIX v3 "ngen" biçimi, uzantısı geliştiriciler artık bildirim derlemelerini yükleme zamanında.

Hangi "ngen" yaptığını anlatan MSDN'den bir alıntı aşağıdadır:

>Yerel Görüntü Oluşturucusu (Ngen.exe), yönetilen uygulamaların performansını artıran bir araçtır. Ngen.exe, işlemciye özel derlenmiş makine kodu içeren dosyalar olan yerel görüntüler oluşturur ve bunları yerel bilgisayarın yerel görüntü önbelleğine yükler. Çalışma zamanı orijinal derlemeyi derlemek için anlık (JIT) derleyiciyi kullanmak yerine önbellekteki yerel görüntüleri kullanabilir.
>
>gelen [Ngen.exe (yerel Görüntü Oluşturucu)](https://msdn.microsoft.com/en-us/library/6t9t5wcf(v=vs.110).aspx)

Derleme bir "ngen" için sırayla VSIX "makine başına örnek başına" yüklenmesi gerekir. Bu extension.vsixmanifest Tasarımcısı'nda "tüm kullanıcılar" onay kutusunu işaretleyerek etkin hale getirilebilir:

![tüm kullanıcılar denetleyin](media/check-all-users.png)

## <a name="how-to-enable-ngen"></a>Ngen etkinleştirme

Bir derlemeyi Ngen etkinleştirmek için kullanabileceğiniz **özellikleri** Visual Studio'daki.

Ayarlanabilir 4 özellikleri şunlardır:

1. **Ngen** (Boole) - Visual Studio yükleyicisi true ise, derleme "ngen" olur.
2. **Ngen uygulama** (dize) - Ngen derleme bağımlılıkları çözümlemek amacıyla bir uygulamanın app.config dosyasına kullanmanıza olanak sağlar. Bu değer, app.config (Visual Studio yükleme dizini göreli) kullanmak istediğiniz bir uygulama için ayarlanmalıdır.
3. **Ngen mimarisi** (numaralandırma) - yerel derlemenizi derlemek için mimarisi. Seçenekler şunlardır: bir. NotSpecified b. X86 c. X64 d. Tümü
4. **Ngen öncelik** (tamsayı) - 1 ile 3 arasında Ngen öncelik düzeyi adresindeki belgelenmiştir [Ngen.exe öncelik düzeyleri](https://msdn.microsoft.com/en-us/library/6t9t5wcf(v=vs.110).aspx#Anchor_3).

Göz atın işte **özellikleri** eylem penceresinde:

![Ngen özellikleri](media/ngen-in-properties.png)

Bu meta verileri VSIX proje .csproj dosya içinde proje başvurusu ekler:

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
    <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
    <Name>ClassLibrary1</Name>
    <Ngen>True</Ngen>
    <NgenApplication>vsn.exe</NgenApplication>
    <NgenArchitecture>X86</NgenArchitecture>
    <NgenPriority>2</NgenPriority>
</ProjectReference>
 ```

 >**Not:** tercih ederseniz, doğrudan .csproj dosyasını düzenleyin.

## <a name="extra-information"></a>Ek bilgi

Özellik Tasarımcı değişiklikleri daha fazlasını proje başvuruları için geçerlidir; Ngen meta veri öğeleri için projenizin içinde ayarlayabilirsiniz (.NET derlemelerini öğeleridir olarak uzun yukarıda açıklanan aynı yöntemleri kullanarak).