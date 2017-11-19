---
title: "Yönetilen kodda hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging managed code
- debugging ASP.NET Web applications, managed code
- managed code, debugging
ms.assetid: fa3aff01-c271-4aa7-b5b1-def560471c84
caps.latest.revision: "34"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 42018230262e17bc99905833da1b15e30a7d62aa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-managed-code"></a>Yönetilen Kodda Hata Ayıklama
Genel hata ayıklama sorunları ve teknikler yönetilen uygulamalar için bu bölümde ele alınmaktadır veya uygulamaları Visual Basic, C# ve C++ gibi ortak dil çalışma zamanı hedefleyen dillerde yazılır. Burada açıklanan teknikleri üst düzey tekniklerle aynıdır. Daha fazla bilgi için bkz: [hata ayıklayıcıyı kullanma](../debugger/debugger-basics.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Çıktı penceresindeki tanılama iletileri](../debugger/diagnostic-messages-in-the-output-window.md)  
 Açıklar <xref:System.Diagnostics.Debug> ve <xref:System.Diagnostics.Trace> ile yazabilirsiniz çalışma zamanı iletileri sınıfları **çıkış** penceresi. Bu sınıfların belirtilen bir koşul başarısız olursa, ayrıca yürütme keser yürütme ve bilgileri çıkış bozmadan bilgileri çıkışını etkinleştirmek çıkış yöntemleri içerir.  
  
 [Yönetilen koddaki onaylar](../debugger/assertions-in-managed-code.md)  
 Bağımsız değişken olarak belirttiğiniz koşullara test yönetilen koddaki onaylar açıklar `Assert` yöntemleri. Ayrıca, bu konu örnek kod, kullanma hakkında bilgi sağlar <xref:System.Diagnostics.Debug> ve <xref:System.Diagnostics.Trace> sınıfı yöntemleri, hata ayıklama ve yayın sürümleri kodunun yan etkileri konuları assert bağımsız değişkenler, özelleştirme assert davranışı ve yapılandırma dosyaları.  
  
 [Visual Basic'deki deyimler Durdur](../debugger/stop-statements-in-visual-basic.md)  
 Açıklar `Stop` kesme noktası ayarlama için bir alternatif sağlayan deyimi. Kod örneği de sağlanır, arasındaki karşılaştırmaları birlikte `Stop` deyimi ve `End` arasında iyi olarak olarak deyimi `Stop` ve `Assert` deyimi.  
  
 [İzlenecek yol: bir Windows formunda hata ayıklama](../debugger/walkthrough-debugging-a-windows-form.md)  
 Bir Windows formu oluşturma ve bu formunda hata ayıklama için adım adım yönergeler sağlar. Windows Form, yönetilen bir Windows uygulamasının standart bir bileşeni en yaygın yönetilen uygulamaların biridir. Bu kılavuzda Visual C# ve Visual Basic kullanır, ancak C++ ile bir Windows formu oluşturma teknikleri genellikle benzerdir.  
  
 [OnStart yönteminde hata ayıklama](../debugger/how-to-debug-the-onstart-method.md)  
 Hata ayıklama olanak tanımak için kod örnekleri sağlar `OnStart` yönetilen bir Windows hizmetini yöntemi. Hata ayıklama için `OnStart` yöntemi bir Windows hizmetinin Hizmet benzetimini yapmak için kod birkaç satırlık eklemeniz gerekir.  
  
 [Karışık mod hata ayıklaması](../debugger/debugging-mixed-mode-applications.md)  
 Karışık mod uygulamalarında hata ayıklama açıklanır. Bu, yönetilen kod ile yerel kod birleştirir herhangi bir uygulama anlamına gelir.  
  
 [Hata: sistemde çekirdek hata ayıklayıcı etkinleştirildiğinden hata ayıklama mümkün değil](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md)  
 Hata ayıklama yönetilen kodu çalışırsanız oluşan bir hata iletisi açıklanır bir [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)], [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)], [!INCLUDE[Win2kFamily](../code-quality/includes/win2kfamily_md.md)], ya da hata ayıklama modunda başlatılan Windows NT sistemi.  
  
 [JIT iyileştirmesi ve hata ayıklama](../debugger/jit-optimization-and-debugging.md)  
 Hata ayıklamayı JIT iyileştirmesi etkilerini açıklar.  
  
 [LINQ ve DLINQ hata ayıklama](../debugger/debugging-linq.md)  
 LINQ sorgularını hata ayıklama teknikleri açıklar.  
  
 [İzlenecek yol: paralel uygulamada hata ayıklama](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Nasıl kullanılacağını açıklar **Paralel Görevler** ve **Paralel Yığınlar** paralel uygulamada hata ayıklamak için windows aracı.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [IntelliTrace](../debugger/intellitrace.md)  
 IntelliTrace ile uygulamanızın yürütme geçmişini kaydetme tarafından hataları daha hızlı ve daha kolay bulabilirsiniz. Geriye doğru adım ve kaydedilen olayları ve zamanında anahtar noktalarda uygulamanızın durumunu incelemek için çağrıları aracılığıyla iletebilir. Kodunuzdaki hataları ayıklamanıza çok sayıda kesme noktalarını ayarlama veya sık olarak uygulamanızı yeniden başlatmayı olmadan. Visual Studio Ultimate gerektirir.  
  
 [İzleme ve uygulamaları](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)  
 İzleme, onu çalıştıran ve düzenleme, karşın, uygulamanızın yürütülmesini izlemek bir yol açıklar stratejik konumlara kodunuzda izleme deyimleri yerleştirme içerir. Bu konu ayrıca araçları bir giriş sağlar ve izleme, izleme anahtarları, uygulama kodunda izleme, uygulama koduna izleme deyimleri ekleme ve ile koşullu derleme dinleyicileri izleme <xref:System.Diagnostics.Debug> ve <xref:System.Diagnostics.Trace> .  
  
 [/ ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute)  
 Ekler bir bağlayıcı seçeneği açıklar <xref:System.Diagnostics.DebuggableAttribute> C++ ile yazılmış bir kod için. Bu öznitelik hata ayıklama kullanmak için gerekli özellikler gibi C++ ile ekleyin.  
  
 [Hata ayıklama Windows hizmet uygulamaları](/dotnet/framework/windows-services/how-to-debug-windows-service-applications)  
 Windows hizmet uygulamalarında hata ayıklama, ayarlama dahil olmak üzere, işlemine iliştirme, hizmetin kodda hata ayıklama konuları sağlar `OnStart` yöntemi ve kodda kesme noktalarını ayarlama ve Hizmetleri denetimi kullanarak ana yöntemi Başlatma, durdurma, duraklatma ve devam hizmetiniz için manager'ı tıklatın.  
  
 [Hata ayıklama ve profil oluşturma](/dotnet/framework/debug-trace-profile/index)  
 Hata ayıklama .NET Framework uygulamaları ve yapılandırma gereksinimleri açıklanır.  
  
 [Komut dosyası ve Web uygulamalarında hata ayıklama](../debugger/debugging-web-applications-and-script.md)  
 Genel hata ayıklama sorunları ve komut dosyası ve Web uygulamalarında hata ayıklama sırasında karşılaşabileceğiniz teknikleri açıklar.  
  
 [Hata ayıklayıcı Visual Studio 2015'teki yenilikler](../debugger/what-s-new-for-the-debugger-in-visual-studio.md)  
 Bu sürümde eklenen yeni hata ayıklama özellikleri açıklaması [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 [Hata ayıklama giriş sayfası](../debugger/debugger-feature-tour.md)  
 Hata ayıklama belge büyük bölümlerine bağlantılar sağlar. Bilgi içeren hata ayıklayıcı, ayarları ve hazırlığı, özel durumların işlenmesi kesme noktaları, yenilikler Düzenle ve devam etmek, yönetilen kodda hata ayıklama, Visual C++ projelerinde hata ayıklama, COM ve ActiveX hata ayıklama, DLL'lerde hata ayıklama, SQL ve kullanıcı hata ayıklama arabirimi başvuruları.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Özel Windows hata ayıklama tasarım zamanında Forms denetimleri](/dotnet/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)  
 [Visual Studio'da hata ayıklamayı](../debugger/index.md) [özelliği turu hata ayıklayıcı](../debugger/debugger-feature-tour.md)