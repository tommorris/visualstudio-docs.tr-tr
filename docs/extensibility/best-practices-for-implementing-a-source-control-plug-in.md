---
title: Kaynak Denetim eklentisi uygulamak için en iyi uygulamalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, best practices
- best practices, source control plug-ins
- source control [Visual Studio SDK], plug-ins
ms.assetid: 85e73b73-29dc-464f-8734-ed308742c435
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d5e9972b28d435f5cba360b2328ecdd6d18eb52e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31106054"
---
# <a name="best-practices-for-implementing-a-source-control-plug-in"></a>Kaynak Denetim eklentisi uygulamak için en iyi yöntemler
Aşağıdaki teknik ayrıntılar güvenilir bir kaynak denetimi eklentide uygulamanıza yardımcı olabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="memory-management-issues"></a>Bellek yönetimi sorunları  
 Çoğu durumda, çağıranın olduğundan, tümleşik geliştirme ortamı (IDE) serbest bırakır ve bellek ayırır. Kaynak Denetim eklentisi içindeki arayana ayrılan arabellekler dizeler ve diğer öğeleri döndürür. Özel durumlar sonuçları ortaya çıktıkları belirli işlevleri açıklamasında belirtilmiştir.  
  
## <a name="arrays-of-file-names"></a>Dosya adları dizileri  
 Dosyaları bir dizi geçirildiğinde, dosya adlarını bitişik bir dizi olarak aktarılmaz. Bu dosya adlarına işaretçileri dizisi geçirilir. Örneğin, [SccGet](../extensibility/sccget-function.md), dosya adları geçirilen `lpFileNames` parametresi, burada `lpFileNames` gösteren bir işaretçidir gerçekte bir `char **`. `lpFileNames`[0] gösteren bir işaretçidir ad `lpFileNames`[1] ikinci adına ve benzeri bir işaretçidir.  
  
## <a name="large-model"></a>Büyük modeli  
 Tüm İşaretçiler 16-bit işletim sistemlerinde bile 32 bit değerleridir.  
  
## <a name="fully-qualified-paths"></a>Tam yollar  
 Burada dosya adlarını veya dizinleri bağımsız değişken olarak belirtilmiş, tam yol veya UNC yolları, bitiş ters eğik çizgi olmadan olması gerekir. Kaynak denetimi için göreli yolların diğer bir deyişle temel alınan kaynak denetim sistemi gereksinimi varsa bu çevirmek için eklenti sorumluluğundadır.  
  
## <a name="specify-a-fully-qualified-path-for-the-registered-dll"></a>Kayıtlı DLL için tam bir yol belirtin  
 IDE DLL'leri artık göreli yolları (örneğin,.\NewProvider.dll) yükler. DLL Dosyasının tam yolu (örneğin, C:\Providers\NewProvider.dll) belirtilmelidir. Bu gereksinim, yetkisiz veya Kimliğine bürünülen kaynak denetimi DLL'leri yüklenmesini engelleyerek IDE güvenlik güçlendirir.  
  
## <a name="check-for-an-existing-vssci-plug-in-when-you-install-your-source-control-plug-in"></a>Kaynak Denetim eklentisi yüklediğinizde eklenti bir varolan VSSCI denetle  
 Kaynak Denetim eklentisi yüklemeye planları bir kullanıcı bilgisayarda yüklü bir var olan kaynak denetimi eklenti zaten sahip olabilir. Yükleme (Kurulum) programı eklenti için oluşturduğunuz ilgili kayıt defteri anahtarları için varolan değerler olup olmadığını belirlemeniz gerekir. Bu anahtarları zaten ayarladıysanız, yükleme programı kullanıcı, eklentiyi Eklenti varsayılan kaynak denetimi kaydetmek ve yüklü bir değiştirmek istemeniz gerekir.  
  
## <a name="error-result-codes-and-reporting"></a>Hata sonuç kodlarını ve Raporlama  
 `SCC_OK` Dönüş kodu için bir kaynak denetimi işlevi gösterir tüm dosyalar için işlemi başarılı oldu. İşlem başarısız olursa, karşılaşılan son hata kodu döndürmesi beklenir.  
  
 Raporlama için IDE içinde bir hata meydana gelirse, IDE raporlama için sorumlu olduğu kuralıdır. Kaynak denetim sistemi bir hata meydana gelirse, raporlama için kaynak denetim eklentisi sorumludur. "Bu dosya zaten kullanıma alındı" eklenti tarafından raporlanması ancak örneği için "hiçbir dosya şu anda seçili" IDE tarafından bildirilen.  
  
## <a name="the-context-structure"></a>Bağlam yapısı  
 Çağrı sırasında [SccInitialize](../extensibility/sccinitialize-function.md), çağıran geçişleri `ppvContext` bir geçersiz kılma için başlatılmamış bir tanıtıcı olan parametre. Kaynak Denetim eklentisi Bu parametre yoksayabilirsiniz veya herhangi bir türde bir yapı ayırın ve bir işaretçi için yapıyı geçirilen işaretçiyi koyun. Bu yapı IDE anlamıyor, ancak bunu bir işaretçi bu yapı için her bir çağrı eklentide içine geçirir. Bu, değerli bağlam önbellek bilgilerini eklentiye bu genel değişkenler kullanmadan işlev çağrıları boyunca devam ederse genel durum bilgilerini saklamak üzere kullanabileceğiniz sağlar. Eklenti yapılan bir çağrı yapısına boşaltma sorumludur [SccUninitialize](../extensibility/sccuninitialize-function.md).  
  
 Eklenti kümeleri `SCC_CAP_REENTRANT` içinde bit [SccInitialize](../extensibility/sccinitialize-function.md) (özellikle `lpSccCaps` parametresi), birden fazla bağlam yapıları açık olan tüm projeleri izlemek için kullanılır.  
  
## <a name="bitflags-and-other-command-options"></a>Bit işaretleri ve diğer komut seçenekleri  
 Her komut gibi [SccGet](../extensibility/sccget-function.md), IDE komut davranışını değiştirmek pek çok seçenek belirleyebilirsiniz.  
  
 API IDE tarafından belirli seçenekleri ayarını destekler `fOptions` parametresi. Bu seçenekler açıklanmaktadır [bit işaretleri belirli komutları tarafından kullanılan](../extensibility/bitflags-used-by-specific-commands.md) etkilediklerini komutları birlikte. Genel olarak, bunlar için kullanıcı olmayan girmeniz istenirdi seçenekleridir.  
  
 Yaygın olarak kaynak denetim eklentileri arasında değiştiğinden en kullanıcı tarafından yapılandırılabilir seçeneklerini ayarlama bu şekilde, tanımlı değil. Bu nedenle, önerilen mekanizmasıdır bir **Gelişmiş** düğmesi. Örneğin, **almak** iletişim kutusu, IDE anladığı, ancak aynı zamanda görüntüler bilgileri görüntüler bir **Gelişmiş** eklenti bu komutla seçenekleri varsa düğmesine tıklayın. Kullanıcı tıkladığında **Gelişmiş** button, IDE çağrıları [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) eklentisinin bit işaretleri veya bir tarih/saat gibi bilgileri kullanıcıdan istemek için kaynak denetimini etkinleştirmek için. Geri sırasında geçirilen bir yapı bu bilgileri eklenti döndürür `SccGet` komutu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim Eklentileri](../extensibility/source-control-plug-ins.md)   
 [Kaynak Denetimi Eklentisi Oluşturma](../extensibility/internals/creating-a-source-control-plug-in.md)