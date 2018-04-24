---
title: ClickOnce uygulamalarını yerelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- WPF, ClickOnce applications
- ClickOnce deployment, globalization
- deploying applications [ClickOnce], localizing ClickOnce applications
- localization, ClickOnce deployment
- ClickOnce deployment, download on-demand
- ClickOnce deployment, localization
- Windows Forms, ClickOnce applications
- console applications, ClickOnce applications
ms.assetid: c92b193b-054d-4923-834b-d4226a4c7a1a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c3d7ebc762c7b1feb895323f7ef9ee0180ce954e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="localizing-clickonce-applications"></a>ClickOnce Uygulamalarını Yerelleştirme
Yerelleştirme, uygulamanızın belirli bir kültür için uygun hale getirme işlemidir. Gerekirse, yansıtma denetimleri sağdan sola ve bu işlem, kullanıcı arabirimi (UI) metni doğru tarih ve para birimi biçimlendirme, bir form üzerinde denetimleri boyutunu ayarlama kullanarak bir bölgeye özgü dile çevirme içerir.  
  
 Bir veya daha fazla uydu derlemeleri oluşturma uygulama sonuçlarınızda yerelleştirme. Her derleme UI dizeler, görüntüler ve verilen bir kültüre özgü diğer kaynakları içerir. (Uygulamanızın ana yürütülebilir dosyanın uygulamanız için varsayılan kültürü için dizeleri içerir.)  
  
 Bu konu dağıtmak için üç yollarını açıklar bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] diğer kültür için uygulama:  
  
-   Tek bir dağıtımda tüm uydu derlemelerini içerir.  
  
-   Her dahil tek bir uydu derlemesi ile her kültür için bir dağıtım oluşturun.  
  
-   Uydu derlemelerini indirme.  
  
## <a name="including-all-satellite-assemblies-in-a-deployment"></a>Bir dağıtımda tüm uydu derlemeleri  
 Yayımlama birden çok yerine [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımlarında, tek bir yayımlayabilirsiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] tüm uydu derlemelerini içeren dağıtım.  
  
 Varsayılan olarak bu yöntemdir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Bu yöntemi kullanmak için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], herhangi bir ek iş yapmak gerekmez.  
  
 Bu yöntem MageUI.exe ile kullanmak için kültürü uygulamanıza ayarlamalısınız **nötr** MageUI.exe içinde. Ardından, el ile tüm uydu derlemelerinin dağıtımınızda eklemeniz gerekir. MageUI.exe, kullanarak uydu derlemelerini ekleyebilirsiniz **Populate** düğmesini **dosyaları** uygulama bildiriminizi sekmesinde.  
  
 Bu yaklaşımın avantajı, tek bir dağıtım oluşturur ve yerelleştirilmiş dağıtım konunuz basitleştirir ' dir. Çalışma zamanında uygun uydu derlemesini, kullanıcının Windows işletim sistemine bağlı olarak kullanılacak varsayılan kültürü kullanılır. Bu yaklaşımın bir dezavantajı, her uygulama yüklendiğinde veya bir istemci bilgisayarda güncelleştirildiğinde, tüm uydu derlemelerini indirir olmasıdır. Uygulamanız çok sayıda dizeleri sahip veya müşterileriniz yavaş ağ bağlantısı varsa, bu işlem uygulama güncelleştirmesi sırasında performansı etkileyebilir.  
  
> [!NOTE]
>  Bu yaklaşım, uygulamanızın yüksekliğini, genişlik ve otomatik olarak farklı bir metin dizesi boyutlarının farklı kültürler uyum sağlayacak şekilde denetimleri konumunu ayarlar varsayar. Windows Forms denetimleri ve kolayca yerelleştirilebilir dahil olmak üzere bir form tasarlamayı olanak tanıyan teknolojileri çeşitli içeren <xref:System.Windows.Forms.FlowLayoutPanel> ve <xref:System.Windows.Forms.TableLayoutPanel> denetimleri yanı sıra <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği.  Ayrıca bkz. [nasıl yapılır: Windows Forms kullanarak AutoSize ve TableLayoutPanel denetimi destek yerelleştirme](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\)).  
  
## <a name="generate-one-deployment-for-each-culture"></a>Her kültür için bir dağıtım oluşturun  
 Bu dağıtım stratejisini birden çok dağıtım oluşturun. Her dağıtımda, yalnızca belirli bir kültür için gerekli uydu derlemeyi dahil etme ve dağıtım kültüre özgü olarak işaretleyin.  
  
 Bu yöntemi kullanmak için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ayarlayın **Dili Yayımla** özelliği **Yayımla** istediğiniz bölgeyi sekmesine. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otomatik olarak seçin ve diğer tüm uydu derlemelerini dağıtımdan hariç bölge için gerekli uydu derlemesini dahil edilir.  
  
 Microsoft MageUI.exe aracını kullanarak aynı şeyi gerçekleştirebilirsiniz [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Kullanım **Populate** düğmesini **dosyaları** diğer tüm uydu derlemelerini uygulama dizininden hariç tutmak ve daha sonra ayarlamak için uygulama bildiriminizi sekmesinde **kültür**alanını **adı** Dağıtım bildiriminizi MageUI.exe sekmesi. Bu adımlar yalnızca doğru derlemeyi içerir, ancak de ayarlar `language` özniteliği `assemblyIdentity` Dağıtım bildiriminizi kültüre karşılık gelen öğe.  
  
 Uygulama yayımlandıktan sonra her ek kültür için bu adımı tekrarlamalısınız uygulama destekler. Farklı bir Web sunucusu veya dosya paylaşımına her seferinde her uygulama bildirimi farklı bir uydu derlemeyi başvurur ve her dağıtım bildirimi içinfarklıbirdeğergerekirçünküyayımladığınızdaneminolmanızgerekir`language`özniteliği.  
  
## <a name="downloading-satellite-assemblies-on-demand"></a>Uydu derlemelerini indirme  
 Tüm uydu derlemelerini tek bir dağıtımda karar verirseniz, derlemeleri isteğe bağlı olarak işaretlemek sağlayan isteğe bağlı indirme, kullanarak performansı geliştirebilir. Uygulama yüklendiğinde veya güncelleştirilmiş işaretlenen derlemeler yüklenmeyecektir. Çağırarak gerektiğinde derlemeler yükleyebilirsiniz <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> yöntemi <xref:System.Deployment.Application.ApplicationDeployment> sınıfı.  
  
 Uydu derlemelerini indirme biraz diğer tür isteğe bağlı derlemeleri indirme farklıdır. Bu senaryoyu kullanarak etkinleştirme hakkında daha fazla bilgi ve kod örnekleri için [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] araçlarını [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], bkz: [izlenecek yol: ClickOnce dağıtım API'si ile isteğe bağlı uydu derlemelerini indirme](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md).  
  
 Bu senaryoda etkinleştirebilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  Ayrıca bkz. [izlenecek yol: ClickOnce dağıtım API'sini kullanarak Tasarımcısı ile isteğe bağlı uydu derlemelerini indirme](http://msdn.microsoft.com/library/ms366788\(v=vs.110\)) veya [izlenecek yol: ClickOnce dağıtım API'si ile isteğe bağlı uydu derlemelerini indirme Tasarımcı kullanarak](http://msdn.microsoft.com/library/ms366788\(v=vs.120\)).  
  
## <a name="testing-localized-clickonce-applications-before-deployment"></a>ClickOnce uygulamaları dağıtmadan önce yerelleştirilmiş test etme  
 Bir Windows Forms uygulaması serileştirilebilmesi için bir uydu derleme kullanılacak <xref:System.Threading.Thread.CurrentUICulture%2A> özelliği uygulamanın ana iş parçacığı için uydu derlemenin kültürü olarak ayarlanır. Yerel pazardaki müşteriler büyük olasılıkla zaten yerelleştirilmiş bir Windows sürümü ile kültüre varsayılan olarak uygun ayarlanmış çalıştırırsınız.  
  
 Uygulamanızı müşteriler için kullanılabilir hale getirmeden önce yerelleştirilmiş dağıtımları test etmek için üç seçeneğiniz vardır:  
  
-   Çalıştırabilirsiniz, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygun bir uygulama yerelleştirilmiş Windows sürümleri.  
  
-   Ayarlayabileceğiniz <xref:System.Threading.Thread.CurrentUICulture%2A> uygulamanızda program aracılığıyla özelliği. (Bu özelliği çağırmadan önce ayarlanmalıdır <xref:System.Windows.Forms.Application.Run%2A> yöntemi.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<assemblyIdentity > öğesi](../deployment/assemblyidentity-element-clickonce-deployment.md)   
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [Windows Forms’u Genelleştirme](/dotnet/framework/winforms/advanced/globalizing-windows-forms)