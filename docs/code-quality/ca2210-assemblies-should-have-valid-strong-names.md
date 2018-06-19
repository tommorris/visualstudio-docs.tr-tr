---
title: 'CA2210: Derlemelerin tanımlayıcı adı geçerli olmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AssembliesShouldHaveValidStrongNames
- CA2210
helpviewer_keywords:
- AssembliesShouldHaveValidStrongNames
- CA2210
ms.assetid: 8ed33d1c-8ec6-4b47-a692-e22dc8693088
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7b7fb5f55ee345fa47a4a4510fe8121b82d1c0ae
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919644"
---
# <a name="ca2210-assemblies-should-have-valid-strong-names"></a>CA2210: Derlemelerin tanımlayıcı adı geçerli olmalıdır
|||
|-|-|
|TypeName|AssembliesShouldHaveValidStrongNames|
|CheckId|CA2210|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Bir derleme tanımlayıcı bir ad ile imzalanmamış güçlü ad doğrulanamadı veya güçlü ad bilgisayarın geçerli kayıt defteri ayarlarını geçerli olmaz.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural alır ve bir derleme tanımlayıcı adı doğrular. Aşağıdakilerden biri doğruysa bir ihlali oluşur:

-   Derleme tanımlayıcı adı yok.

-   Derleme imzalama sonra değiştirildi.

-   Derleme gecikme imzalanır.

-   Derleme yanlış imzalı veya imzalama başarısız oldu.

-   Derleme doğrulama geçirmek kayıt defteri ayarları gerektirir. Örneğin, derleme için doğrulama atlamak için tanımlayıcı ad Aracı (Sn.exe) kullanıldı.

 Güçlü ad oynanmış derlemeyi bilmeden yükleyerek istemcileri korur. Güçlü adı olmayan derlemeler oldukça sınırlı sayıda senaryo dışında kullanılmamalıdır. Düzgün imzalanmamış derlemeleri paylaşırsanız veya dağıtırsanız, derleme aslı bozuabilir, ortak dil çalışma zamanı derlemeyi yükleyemeyebilir veya kullanıcı kendi bilgisayarındaki doğrulamayı devre dışı bırakabilir. Bir derleme tanımlayıcı adı olmadan aşağıdaki dezavantajları vardır:

-   Kendi çıkış doğrulanamıyor.

-   Ortak dil çalışma zamanı derlemesi içeriğini değiştirilmiş, kullanıcıları uyarın olamaz.

-   Genel derleme önbelleğine yüklenemiyor.

 Yük ve gecikme imzalı bir derleme çözümlemek için derleme için doğrulama devre dışı bırakmalısınız olduğunu unutmayın.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 **Bir anahtar dosyası oluşturmak için**

 Aşağıdaki yordamlardan birini kullanın:

-   Tarafından sağlanan derleme bağlayıcı aracını (Al.exe) [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] SDK.

-   İçin [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] v1.0 ya da v1.1, kullanın ya da <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> veya <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName> özniteliği.

-   İçin [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], kullanın ya da `/keyfile` veya `/keycontainer` derleyici seçeneği [/keyfile (anahtar belirtin veya anahtar çiftini derlemeyi imzalamak için)](/cpp/build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly) veya  [ /keycontainer (derlemeyi imzalamak için bir anahtar kapsayıcısı belirtin)](/cpp/build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly) c++ bağlayıcı seçeneği).

 **Visual Studio'da tanımlayıcı adla derlemenizi imzalamak için**

1.  İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], çözümünüzü açın.

2.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **özellikleri.**

3.  Tıklatın **imzalama** sekmesini tıklatın ve seçin **derlemeyi imzalamak** onay kutusu.

4.  Gelen **güçlü ad anahtar dosyası seçin**seçin **yeni**.

     **Güçlü ad anahtarı oluştur** penceresi görüntülenir.

5.  İçinde **anahtar dosya adını**, güçlü ad anahtar için bir ad yazın.

6.  Anahtarı bir parolayla koruyun ve ardından isteyip istemediğinizi seçin **Tamam**.

7.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **yapı**.

 **Visual Studio dışında tanımlayıcı adla derlemenizi imzalamak için**

-   Tarafından sağlanan tanımlayıcı ad Aracı (Sn.exe) [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] SDK. Daha fazla bilgi için bkz: [Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool).

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Derleme bir ortamda kullanılırsa, yalnızca bir bu kuraldan gizlemek içerikle oynama ilgili bir sorun olmadığı.

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName> [Nasıl yapılır: bir derlemeyi tanımlayıcı adla oturum](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name) [Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool)