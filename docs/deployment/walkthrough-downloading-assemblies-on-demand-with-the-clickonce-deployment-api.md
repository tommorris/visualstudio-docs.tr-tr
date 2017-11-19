---
title: "İzlenecek yol: ClickOnce dağıtım API'si ile isteğe bağlı derlemeleri indirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- assemblies, downloading [ClickOnce]
- ClickOnce deployment, on-demand download
- on-demand assemblies, ClickOnce
ms.assetid: d20e2789-8621-4806-b5b7-841122da1456
caps.latest.revision: "16"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: f84d1cfa2208dc8a8b9d279a46ecf52676c0ae62
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api"></a>İzlenecek yol: ClickOnce Dağıtım API'si ile İsteğe Bağlı Derlemeleri İndirme
Varsayılan olarak, tüm derlemeler dahil bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamayı ilk kez çalıştırdığınızda uygulama yüklenir. Bununla birlikte, bir dizi kullanıcılarınız tarafından kullanılan uygulamanızın parçalarını olabilir. Bu durumda, yalnızca türlerinden birini oluşturduğunuzda bütünleştirilmiş kodu indirmek istediğiniz. Aşağıdaki örneklerde, belirli derlemeleri "isteğe bağlı" olarak işaretlemek gösterilmiştir ve bunları kullanarak indirmek nasıl sınıfları <xref:System.Deployment.Application> ortak dil çalışma zamanı (CLR) bunları talep ettiğinde ad alanı.  
  
> [!NOTE]
>  Uygulamanız bu yordamı kullanmak için tam güvende çalıştırmanız gerekir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlerden biri gerekir:  
  
-   Windows SDK. Windows SDK'sı Microsoft Download Center'dan gelen indirilebilir.  
  
-   Visual Studio.  
  
## <a name="creating-the-projects"></a>Proje oluşturma  
  
#### <a name="to-create-a-project-that-uses-an-on-demand-assembly"></a>İsteğe bağlı bütünleştirilmiş kullanan bir proje oluşturmak için  
  
1.  ClickOnceOnDemand adlı bir dizin oluşturun.  
  
2.  Windows SDK komut istemi açın veya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komut istemi.  
  
3.  ClickOnceOnDemand dizinine değiştirin.  
  
4.  Aşağıdaki komutu kullanarak bir genel/özel anahtar çifti oluşturur:  
  
    ```  
    sn -k TestKey.snk  
    ```  
  
5.  Not Defteri'nde veya başka bir metin düzenleyicisi kullanarak tanımlarsınız adlı bir sınıf `DynamicClass` adlı tek bir özellik ile `Message`.  
  
     [!code-vb[ClickOnceLibrary#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_1.vb)]
     [!code-csharp[ClickOnceLibrary#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_1.cs)]  
  
6.  Metin adlı bir dosya olarak kaydetmek `ClickOnceLibrary.cs` veya `ClickOnceLibrary.vb`kullanın, ClickOnceOnDemand dizinine dil bağlı olarak.  
  
7.  Bir derlemeye dosyasını derleyin.  
  
    ```csharp  
    csc /target:library /keyfile:TestKey.snk ClickOnceLibrary.cs  
    ```  
  
    ```vb  
    vbc /target:library /keyfile:TestKey.snk ClickOnceLibrary.vb  
    ```  
  
8.  Derleme için ortak anahtar belirteci almak için aşağıdaki komutu kullanın:  
  
    ```  
    sn -T ClickOnceLibrary.dll  
    ```  
  
9. Düzenleyici metninizi kullanarak yeni bir dosya oluşturun ve aşağıdaki kodu girin. Bu kod, gerekli olduğunda, ClickOnceLibrary derlemesini indiren bir Windows Forms uygulaması oluşturur.  
  
     [!code-csharp[ClickOnceOnDemandCmdLine#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_2.cs)]
     [!code-vb[ClickOnceOnDemandCmdLine#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_2.vb)]  
  
10. Kod içinde çağrısı bulun <xref:System.Reflection.Assembly.LoadFile%2A>.  
  
11. Ayarlama`PublicKeyToken` , daha önce aldığınız değeri.  
  
12. Dosya olarak kaydetmek `Form1.cs` veya `Form1.vb`.  
  
13. Aşağıdaki komutu kullanarak bir yürütülebilir dosyada derleyin.  
  
    ```csharp  
    csc /target:exe /reference:ClickOnceLibrary.dll Form1.cs  
    ```  
  
    ```vb  
    vbc /target:exe /reference:ClickOnceLibrary.dll Form1.vb  
    ```  
  
## <a name="marking-assemblies-as-optional"></a>Derlemeleri isteğe bağlı olarak işaretleme  
  
#### <a name="to-mark-assemblies-as-optional-in-your-clickonce-application-by-using-mageuiexe"></a>MageUI.exe kullanarak derlemeleri ClickOnce uygulamanızda isteğe bağlı olarak işaretlemek için  
  
1.  MageUI.exe kullanarak bir uygulama bildirimi oluşturun açıklandığı gibi [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Uygulama bildirimi için aşağıdaki ayarları kullanın:  
  
    -   Uygulama bildirimini ad `ClickOnceOnDemand`.  
  
    -   Üzerinde **dosyaları** sayfasında, ClickOnceLibrary.dll, ayarlayın **dosya türü** sütuna **hiçbiri**.  
  
    -   Üzerinde **dosyaları** ClickOnceLibrary.dll satırda türü sayfası `ClickOnceLibrary.dll` içinde **grup** sütun.  
  
2.  MageUI.exe kullanarak bir dağıtım bildirimi oluşturun açıklandığı gibi [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Dağıtım bildirimi için aşağıdaki ayarları kullanın:  
  
    -   Dağıtım bildirimi ad `ClickOnceOnDemand`.  
  
## <a name="testing-the-new-assembly"></a>Yeni bir derleme test etme  
  
#### <a name="to-test-your-on-demand-assembly"></a>İsteğe bağlı derlemenizi sınamak için  
  
1.  Karşıya yükleme, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bir Web sunucusu dağıtımına.  
  
2.  İle dağıtılan uygulamanızı başlatın [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimine URL'yi girerek bir Web tarayıcısından. Çağırırsanız, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama `ClickOnceOnDemand`ve adatum.com kök dizinine karşıya yükleme, URL'nizi şuna benzer:  
  
    ```  
    http://www.adatum.com/ClickOnceOnDemand/ClickOnceOnDemand.application  
    ```  
  
3.  Ana form görüntülendiğinde basın <xref:System.Windows.Forms.Button>. "Hello, World!" okuyan bir ileti kutusu penceresinde bir dize görmeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Deployment.Application.ApplicationDeployment>