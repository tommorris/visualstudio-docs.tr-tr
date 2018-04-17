---
title: 'Nasıl yapılır: bir çevrimiçi ClickOnce uygulamasında sorgu dize bilgilerini alma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, query strings
- query strings, retrieving information
ms.assetid: 48ce098a-a075-481b-a5f5-c8ba11f63120
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: ae316f8ed84658c96d78f25f2aaf9c64a800d42c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-retrieve-query-string-information-in-an-online-clickonce-application"></a>Nasıl yapılır: Çevrimiçi bir ClickOnce Uygulamasında Sorgu Dize Bilgilerini Alma
*Sorgu dizesi* ile başlayan bir URL biçiminde rasgele bilgi içeren soru işareti (?) sahip bölümüdür *ad = değer*. Sahip olduğunuz varsayalım bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] adlı uygulaması `WindowsApp1` üzerinde barındıran `servername`, ve değişken için bir değer geçirmek istediğiniz `username` zaman uygulamasını başlatır. URL'niz aşağıdakine benzeyebilir:  
  
 `http://servername/WindowsApp1.application?username=joeuser`  
  
 Aşağıdaki iki yordamdan kullanmayı gösteren bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] sorgu dize bilgilerini elde etmek için uygulama.  
  
> [!NOTE]
>  Uygulamanızı bir dosya paylaşımı veya yerel dosya sistemine kullanmak yerine HTTP kullanarak başlatıldığında bilgileri yalnızca bir sorgu dizesi olarak geçirebilirsiniz.  
  
 İlk yordam gösterir nasıl, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, uygulama başlatıldığında bu değerleri okumak için küçük paylaştırılabilen bir kod kullanabilirsiniz.  
  
 Sonraki yordam nasıl yapılandırılacağı gösterilmektedir, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] sorgu dizesi parametreleri kabul edebilmesi için MageUI.exe kullanarak uygulama. Uygulamanızı yayımlama olduğunda bunun gerekecektir.  
  
> [!NOTE]
>  Bu özelliği etkinleştirmek için bir karar vermeden önce bu konunun devamındaki "Güvenlik" bölümüne bakın.  
  
 Nasıl oluşturulacağı hakkında bilgi için bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Mage.exe veya MageUI.exe kullanarak dağıtım bkz [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
> [!NOTE]
>  .NET Framework 3.5 SP1'de başlayarak, komut satırı bağımsız değişkenleri bir çevrimdışı olarak geçirmek mümkündür [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. Uygulama bağımsız değişkenleri eklemek istiyorsanız, kısayol dosyası ile parametrelerinde geçirebilirsiniz. APPREF MS uzantısı.  
  
### <a name="to-obtain-query-string-information-from-a-clickonce-application"></a>Bir ClickOnce uygulamasında sorgu dize bilgilerini almak için  
  
1.  Aşağıdaki kod projenize koyun. Bu kodun çalışması sırayla, System.Web başvuru varsa ve eklemek zorunda kalacaksınız `using` veya `Imports` System.Web, System.Collections.Specialized ve System.Deployment.Application bildirimlerini.  
  
     [!code-csharp[ClickOnceQueryString#1](../deployment/codesnippet/CSharp/how-to-retrieve-query-string-information-in-an-online-clickonce-application_1.cs)]
     [!code-vb[ClickOnceQueryString#1](../deployment/codesnippet/VisualBasic/how-to-retrieve-query-string-information-in-an-online-clickonce-application_1.vb)]  
  
2.  Almak için önceden tanımlanmış bir işlevi çağırmak bir <xref:System.Collections.DictionaryBase.Dictionary%2A> ada göre sıralanan sorgu dizesi parametreleri.  
  
### <a name="to-enable-query-string-passing-in-a-clickonce-application-with-mageuiexe"></a>Sorgu dizesi MageUI.exe ile ClickOnce uygulamasında geçirmeyi etkinleştirmek için  
  
1.  .NET komut istemi açıp aşağıdakini yazın:  
  
    ```  
    MageUI  
    ```  
  
2.  Gelen **dosya** menüsünde, select **açmak**ve dağıtım bildirimini açın, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dosya uygulama biten `.application` uzantısı.  
  
3.  Seçin **dağıtım seçenekleri** panel sol gezinti penceresinde ve seçin **uygulamaya geçirilecek izin URL parametreleri** onay kutusu.  
  
4.  Gelen **dosya** menüsünde, select **kaydetmek**.  
  
> [!NOTE]
>  Alternatif olarak, sorgu dizesi içinde geçirmeyi etkinleştirebilirsiniz [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. Seçin **uygulamaya geçirilecek izin URL parametreleri** açarak bulunabilir onay kutusunu **proje özellikleri**, seçme **Yayımla** tıklatarak sekmesi **Seçenekleri** düğmesine ve ardından seçerek **bildirimleri**.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Sorgu dizesi parametreleri kullandığınızda, dikkat etmenizi uygulamanızı nasıl yüklü ve etkinleştirilmiş. Uygulamanız, kullanıcının bilgisayarındaki Web veya bir ağ paylaşımından yüklemek için yapılandırılmışsa, kullanıcı uygulamayı yalnızca bir kez URL yoluyla etkinleştirecektir olasıdır. Bundan sonra kullanıcı kısayol kullanarak uygulamanızı genellikle etkinleştirecektir **Başlat** menüsü. Sonuç olarak, uygulamanızın yaşam süresi boyunca sorgu dizesi bağımsız değişkenleri yalnızca bir kez alması sağlanır. Bu bağımsız değişkenler gelecekte kullanım için kullanıcının makinesinde depolamayı seçerseniz, güvenli ve güvenli bir şekilde depolamak için sorumludur.  
  
 Uygulamanız yalnızca çevrimiçi ise, her zaman bir URL aracılığıyla etkinleştirilir. Bu durumda bile, ancak, uygulamanızın sorgu dizesi parametreleri eksik veya bozuk durumda olduğunda düzgün çalışması için yazılmış olmalıdır.  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 URL parametreleri izin, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] kullanmadan önce kötü amaçlı karakter girişlerini temizlemeyi planlıyorsanız uygulama. Bir dize tırnak işareti, eğik çizgi veya noktalı virgül, örneğin katıştırılmış, rasgele verileri kullandıysanız bir veritabanında bir SQL sorgu filtrelenmemiş işlemleri. Sorgu dizesi güvenliği hakkında daha fazla bilgi için bkz: [komut dosyası yararlanan genel bakış](http://msdn.microsoft.com/Library/772c7312-211a-4eb3-8d6e-eec0aa1dcc07).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulamalarının Güvenliğini Sağlama](../deployment/securing-clickonce-applications.md)