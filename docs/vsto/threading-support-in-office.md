---
title: Office'te iş parçacığı desteği
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- multiple threads [Office development in Visual Studio]
- threading [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], threading support
- object models [Office development in Visual Studio], threading support
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 966f012b2ff4860205186410951b759c2e214668
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693090"
---
# <a name="threading-support-in-office"></a>Office'te iş parçacığı desteği
  Bu makalede, iş parçacığı oluşturma Microsoft Office nesne modelinde nasıl desteklenir hakkında bilgi sağlar. Office nesne modeli iş parçacığı güvenli değildir, ancak Office çözümü birden çok iş parçacığı çalışmak mümkündür. Office uygulamaları Bileşen Nesne Modeli (COM) sunucularıdır. COM çağırmasına rasgele iş parçacıklarında COM sunucuları izin verir. İş parçacığı güvenli olmayan COM sunucuları için COM yalnızca bir mantıksal iş parçacığı sunucu üzerinde herhangi bir zamanda yürütür. böylece eş zamanlı çağrıları seri hale getirmek için bir mekanizma sağlar. Bu mekanizma tek iş parçacıklı (STA) model olarak bilinir. Çağrıları seri hale getirilmiş olduğundan sunucu meşgul veya diğer çağrılar arka plan iş parçacığında işleme sırasında arayanlar süreyle engellenmiş olabilir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="knowledge-required-when-using-multiple-threads"></a>Bilgi Bankası birden çok iş parçacığı kullanılırken gereklidir  
 Birden çok iş parçacığı ile çalışmak için şu yönlerini en az temel bilgiye sahip çoklu iş parçacığı kullanımı:  
  
-   Windows API'ları  
  
-   COM birden çok iş parçacıklı kavramları  
  
-   Eşzamanlılık  
  
-   Eşitleme  
  
-   Hazırlama  
  
 Genel bilgiler hakkında çoklu iş parçacığı kullanımı, bkz: [yönetilen iş parçacığı oluşturma](/dotnet/standard/threading/).  
  
 Office ana STA içinde çalıştırır Etkilerini anlamak, Office ile çoklu iş parçacığı kullanmayı öğrenme mümkün kılar.  
  
## <a name="basic-multithreading-scenario"></a>Temel Çoklu iş parçacığı kullanımı senaryosu  
 Office çözümlerinde kod her zaman ana kullanıcı Arabirimi iş parçacığı üzerinde çalışır. Arka plan iş parçacığında ayrı bir görev çalıştırarak uygulama performansı kesintisiz isteyebilirsiniz. İki görevleri görünen aynı anda yerine sorunsuz yürütme (birden çok iş parçacığı kullanmak için ana neden) sonuçlanması gereken diğer tarafından izlenen bir görevi tamamlamak için belirtilir. Örneğin, ana Excel UI iş parçacığında olay kodunuz olabilir ve arka plan iş parçacığında bir sunucudan verileri toplar ve sunucu verilerle Excel UI hücrelerde güncelleştiren bir görev çalıştırabilirsiniz.  
  
## <a name="background-threads-that-call-into-the-office-object-model"></a>Office nesne modeline çağrılan arka plan iş parçacıkları  
 Arka plan iş parçacığı Office uygulaması için bir çağrı yaptığında, çağrı otomatik olarak STA sınırına çapraz başvuruya. Ancak, Office uygulamasının arka plan iş parçacığı kolaylaştırır çağrısı anda işleyebilir garanti yoktur. Çeşitli nedenleri olabilir:  
  
1.  Office uygulaması girmek için fırsatınız çağrısı için ileti göndermelidir. Yapıyorsa, bu ağır işlemeler zaman alabilir.  
  
2.  Başka bir mantıksal iş parçacığı zaten grupta ise, yeni bir iş parçacığı giremezsiniz. Bu durum, genellikle mantıksal iş parçacığı Office uygulamasının girdiği ve desteklemeyeceğini çağrı yapanın Grup Geri yapar oluşur. Uygulamayı döndürmek bu arama için bekleniyor engellendi.  
  
3.  Gelen bir arama hemen veremeyecek Excel bir durumda olabilir. Örneğin, Office uygulamasının kalıcı bir iletişim kutusu görüntüleniyor.  
  
 2 ve 3 olasılıkları için COM sağlar [ı](http://msdn.microsoft.com/en-us/e12d48c0-5033-47a8-bdcd-e94c49857248) arabirimi. Sunucu uygularsa, tüm çağrılar aracılığıyla girer [HandleIncomingCall](http://msdn.microsoft.com/en-us/7e31b518-ef4f-4bdd-b5c7-e1b16383a5be) yöntemi. 2 olasılığı için çağrıları otomatik olarak reddedilir. 3 olasılığı için sunucu koşullara bağlı olarak çağrı reddedebilirsiniz. Çağrı reddedilirse, çağıran yapmanız gerekenler karar vermeniz gerekir. Normalde, çağıran uygulayan [ı](http://msdn.microsoft.com/en-us/e12d48c0-5033-47a8-bdcd-e94c49857248), bu durumda, reddetme tarafından size bildirilecektir [IMessageFilter](http://msdn.microsoft.com/en-us/3f800819-2a21-4e46-ad15-f9594fac1a3d) yöntemi.  
  
 Ancak, Visual Studio'da Office geliştirme araçlarını kullanarak oluşturulan çözümlerde, COM birlikte çalışma için tüm reddedilen çağrıları dönüştürür bir <xref:System.Runtime.InteropServices.COMException> ("İleti Filtresi uygulama meşgul gösterilen"). Nesne modeli çağrısı yaptığınızda arka plan iş parçacığında, bu özel durumu işlemek hazırlıklı olmalıdır. Genellikle, belirli bir miktar yeniden deneniyor ve bir iletişim kutusu görüntüleniyor içerir. Ancak, STA olarak arka plan iş parçacığı oluşturabilir ve ardından bu durumu işlemek o iş parçacığı için bir ileti filtresi kaydedin.  
  
## <a name="start-the-thread-correctly"></a>İş parçacığı doğru Başlat  
 Yeni bir STA iş parçacığı oluşturduğunuzda, iş parçacığı başlamadan önce Grup durumu için STA ayarlayın. Aşağıdaki kod örneğinde bunun nasıl yapılacağı gösterilmektedir.  
  
 [!code-csharp[Trin_VstcoreCreatingExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/ThisWorkbook.cs#5)]
 [!code-vb[Trin_VstcoreCreatingExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/ThisWorkbook.vb#5)]  
  
 Daha fazla bilgi için bkz: [yönetilen en iyi yöntemler iş parçacığı oluşturma](/dotnet/standard/threading/managed-threading-best-practices).  
  
## <a name="modeless-forms"></a>Kalıcı olmayan formlar  
 Formun görüntülenirken geçici bir form uygulama ile bazı tür sağlar. Kullanıcı form ile etkileşim ve formu kapatmadan uygulama ile etkileşim kurar. Office nesne modeli yönetilen kalıcı olmayan formları destekler; Ancak, bunlar bir arka plan iş parçacığı üzerinde kullanılmamalıdır.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Yönetilen iş parçacığı oluşturma](/dotnet/standard/threading/)  
 [(C#) iş parçacığı oluşturma](/dotnet/csharp/programming-guide/concepts/threading/index) [iş parçacığı oluşturma (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/threading/index)   
 [Kullanım iş parçacıkları ve iş parçacığı oluşturma](/dotnet/standard/threading/using-threads-and-threading)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)  
  
  