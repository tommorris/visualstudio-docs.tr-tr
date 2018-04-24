---
title: "İzlenecek yol: ClickOnce dağıtım API'si ile uydu derlemelerini indirme | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, globalization
- localization, Windows Forms
- Windows Forms, localization
- globalization, ClickOnce
- satellite assemblies, ClickOnce
- ClickOnce deployment, on-demand download
- localization, ClickOnce deployment
- ClickOnce deployment, localization
ms.assetid: fdaa553f-a27e-44eb-a4e2-08c122105a87
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7b686feb370ff522b2b26866990cc8069b465d96
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api"></a>İzlenecek yol: ClickOnce Dağıtım API'si ile Uydu Derlemelerini İndirme
Windows Forms uygulamaları uydu derlemelerini kullanarak birden çok kültür için yapılandırılabilir. A *uydu derleme* uygulamanın varsayılan kültürü dışında bir kültür için uygulama kaynaklarını içeren bir derlemedir.  
  
 ' Da anlatıldığı gibi [ClickOnce uygulamalarını yerelleştirme](../deployment/localizing-clickonce-applications.md), aynı içinde birden fazla kültür için birden çok uydu derlemelerini içerebilir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım. Varsayılan olarak, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] tek bir istemci, büyük olasılıkla yalnızca bir uydu derlemesi gerekmesine rağmen uydu derlemelerini dağıtımınızdaki tüm istemci makineye indirir.  
  
 Bu kılavuz, uydu derlemelerini isteğe bağlı olarak işaretler ve bir istemci makine bilgisayarın geçerli kültür ayarları için ihtiyaç duyduğu derlemeyi yüklemek gösterilmiştir. Aşağıdaki yordam kullanılabilen araçlar kullanır [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Bu görevde de gerçekleştirebilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  Ayrıca bkz. [izlenecek yol: ClickOnce dağıtım API'sini kullanarak Tasarımcısı ile isteğe bağlı uydu derlemelerini indirme](http://msdn.microsoft.com/library/ms366788\(v=vs.110\)) veya [izlenecek yol: ClickOnce dağıtım API'si ile isteğe bağlı uydu derlemelerini indirme Tasarımcı kullanarak](http://msdn.microsoft.com/library/ms366788\(v=vs.120\)).  
  
> [!NOTE]
>  Test amacıyla, aşağıdaki kod örneğinde program aracılığıyla kültürü ayarlar `ja-JP`. Bu kodu bir üretim ortamı için ayarlama hakkında bilgi için bu konunun devamındaki "Sonraki adımlar" bölümüne bakın.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu konu, Visual Studio kullanarak uygulamanızı yerelleştirilmiş kaynaklar ekleme bildiğinizi varsayar. Ayrıntılı yönergeler için bkz: [izlenecek yol: Windows Formları yerelleştirme](https://msdn.microsoft.com/en-us/library/vstudio/y99d1cd3\(v=vs.100\).aspx).  
  
### <a name="to-download-satellite-assemblies-on-demand"></a>Uydu derlemelerini yüklemek için  
  
1.  Uygulamanızı uydu derlemelerinin isteğe bağlı indirmesini sağlamak için aşağıdaki kodu ekleyin.  
  
     [!code-csharp[ClickOnce.SatelliteAssembliesSDK#1](../deployment/codesnippet/CSharp/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api_1.cs)]
     [!code-vb[ClickOnce.SatelliteAssembliesSDK#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api_1.vb)]  
  
2.  Kullanarak, uygulamanız için uydu derlemeleri oluşturma [Resgen.exe (kaynak dosya oluşturucu)](/dotnet/framework/tools/resgen-exe-resource-file-generator) veya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
3.  Bir uygulama bildirimi oluşturmak veya var olan uygulama bildiriminizi MageUI.exe kullanarak açın. Bu araç hakkında daha fazla bilgi için bkz: [MageUI.exe (bildirim üretme ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client).  
  
4.  Tıklatın **dosyaları** sekmesi.  
  
5.  Tıklatın **üç nokta** düğmesi (**...** ) ve tüm uygulamanızın derlemeler ve oluşturulan Resgen.exe kullanarak uydu derlemelerini dahil dosyaları içeren dizini seçin. (Bir uydu derleme biçiminde bir ada sahip olacaktır *isoCode*\ApplicationName.resources.dll, burada *isoCode* RFC 1766 biçiminde dil tanımlayıcısıdır.)  
  
6.  Tıklatın **Populate** dağıtımınıza dosyaları eklemek için.  
  
7.  Seçin **isteğe bağlı** her uydu derlemesi için onay kutusunu işaretleyin.  
  
8.  Her uydu derlemesi ISO dil tanımlayıcısını için grubu alanını ayarlayın. Örneğin, Japonca uydu derlemesi için indirme grup adını belirtirsiniz `ja-JP`. Bu kullanıcının bağlı olarak uygun uydu dosyasını indirmek için 1. adımda eklediğiniz kodun etkinleştirecek <xref:System.Threading.Thread.CurrentUICulture%2A> özellik ayarı.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bir üretim ortamında, büyük olasılıkla satır ayarlar aşağıdaki kod örneğinde kaldırmanız gerekecek <xref:System.Threading.Thread.CurrentUICulture%2A> belirli bir değere istemci makinelere doğru değerine ayarlanmış olduğundan varsayılan olarak. Örneğin, uygulamanız Japonca istemci makine üzerinde çalıştığında, <xref:System.Threading.Thread.CurrentUICulture%2A> olacaktır `ja-JP` varsayılan olarak. Bu değer programlı olarak ayarlama, uygulamanızı dağıtmadan önce uydu derlemeleri test etmek için iyi bir yoludur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulamalarını Yerelleştirme](../deployment/localizing-clickonce-applications.md)