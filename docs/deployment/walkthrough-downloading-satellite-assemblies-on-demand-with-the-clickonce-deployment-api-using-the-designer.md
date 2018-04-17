---
title: "İzlenecek yol: ClickOnce dağıtım Tasarımcısı'nı kullanarak API'si ile uydu derlemelerini indirme | Microsoft Docs"
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
- Windows Forms, globalization
- ClickOnce deployment, globalization
- localization, Windows Forms
- ClickOnce, on-demand download
- Windows Forms, localization
- ClickOnce deployment, localization
- walkthroughs, localization
ms.assetid: 82b85a47-b223-4221-a17c-38a52c3fb6e2
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 3ee36095e0bd6945f4f382531ee114da3ac50c41
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer"></a>İzlenecek yol: Tasarımcıyı Kullanarak ClickOnce Dağıtım API'si ile Uydu Derlemelerini İndirme
Windows Forms uygulamaları uydu derlemelerini kullanarak birden çok kültür için yapılandırılabilir. A *uydu derleme* uygulamanın varsayılan kültürü dışında bir kültür için uygulama kaynaklarını içeren bir derlemedir.  
  
 ' Da anlatıldığı gibi [ClickOnce uygulamalarını yerelleştirme](../deployment/localizing-clickonce-applications.md), aynı içinde birden fazla kültür için birden çok uydu derlemelerini içerebilir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım. Varsayılan olarak, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] tek bir istemci, büyük olasılıkla yalnızca bir uydu derlemesi gerekmesine rağmen uydu derlemelerini dağıtımınızdaki tüm istemci makineye indirir.  
  
 Bu kılavuz, uydu derlemelerini isteğe bağlı olarak işaretler ve bir istemci makine bilgisayarın geçerli kültür ayarları için ihtiyaç duyduğu derlemeyi yüklemek gösterilmiştir.  
  
> [!NOTE]
>  Test amacıyla, aşağıdaki kod örnekleri program aracılığıyla kültürü kümesine `ja-JP`. Bu kodu bir üretim ortamı için ayarlama hakkında bilgi için bu konunun devamındaki "Sonraki adımlar" bölümüne bakın.  
  
### <a name="to-mark-satellite-assemblies-as-optional"></a>Uydu derlemeleri isteğe bağlı olarak işaretlemek için  
  
1.  Projenizi yapılandırın. Bu işlem için yerelleştirme kültürler için uydu derlemelerini oluşturur.  
  
2.  Çözüm Gezgini'nde proje adına sağ tıklayın ve **özellikleri**.  
  
3.  Tıklatın **Yayımla** sekmesini ve ardından **uygulama dosyalarını**.  
  
4.  Seçin **tüm dosyaları göster** uydu derlemelerini görüntülemek için onay kutusunu. Varsayılan olarak, tüm uydu derlemelerini dağıtımınızda dahil edilecek ve bu iletişim kutusunda görünür olacaktır.  
  
     Uydu derlemesi biçiminde bir ada sahip olacaktır *isoCode*\ApplicationName.resources.dll, burada *isoCode* RFC 1766 biçiminde dil tanımlayıcısıdır.  
  
5.  Tıklatın **yeni...**  içinde **indirme grubu** her dil tanımlayıcısı için listesi. İndirme grubu adı için istendiğinde dil tanımlayıcısını girin. Örneğin, Japonca uydu derlemesi için indirme grup adını belirtirsiniz `ja-JP`.  
  
6.  Kapat **uygulama dosyalarını** iletişim kutusu.  
  
### <a name="to-download-satellite-assemblies-on-demand-in-c"></a>C# uydu derlemelerini yüklemek için #
  
1.  Program.cs dosyasını açın. Bu dosya Çözüm Gezgini'nde, projenize seçin görmüyorsanız ve üzerinde **proje** menüsünde tıklatın **tüm dosyaları göster**.  
  
2.  Uygun uydu derlemesini indirmek ve uygulamanızı başlatmak için aşağıdaki kodu kullanın.  
  
     [!code-csharp[ClickOnce.SatelliteAssemblies#1](../deployment/codesnippet/CSharp/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_1.cs)]  
  
### <a name="to-download-satellite-assemblies-on-demand-in-visual-basic"></a>Visual Basic'te uydu derlemelerini yüklemek için  
  
1.  İçinde **özellikleri** uygulaması için'ı tıklatıp **uygulama** sekmesi.  
  
2.  Sekme sayfasının en altında tıklatın **uygulama olaylarını görüntüle**.  
  
3.  Aşağıdaki içeri aktarmaları ApplicationEvents.VB dosyasının başlangıcına ekleyin.  
  
     [!code-vb[ClickOnce.SatelliteAssembliesVB#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_2.vb)]  
  
4.  Aşağıdaki kodu ekleyin `MyApplication` sınıfı.  
  
     [!code-vb[ClickOnce.SatelliteAssembliesVB#2](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_3.vb)]  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bir üretim ortamında, büyük olasılıkla satır ayarlar kod örneklerinde kaldırmanız gerekecek <xref:System.Threading.Thread.CurrentUICulture%2A> belirli bir değere istemci makinelere doğru değerine ayarlanmış olduğundan varsayılan olarak. Örneğin, uygulamanız Japonca istemci makine üzerinde çalıştığında, <xref:System.Threading.Thread.CurrentUICulture%2A> olacaktır `ja-JP` varsayılan olarak. Programlı olarak ayarlama, uygulamanızı dağıtmadan önce uydu derlemeleri test etmek için iyi bir yoludur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: ClickOnce dağıtım API'si ile uydu derlemelerini indirme](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)   
 [ClickOnce Uygulamalarını Yerelleştirme](../deployment/localizing-clickonce-applications.md)
