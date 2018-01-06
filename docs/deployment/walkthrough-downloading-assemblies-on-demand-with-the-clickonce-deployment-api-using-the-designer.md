---
title: "İzlenecek yol: ClickOnce dağıtım Tasarımcısı'nı kullanarak API'si ile isteğe bağlı derlemeleri indirme | Microsoft Docs"
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
- Windows applications, ClickOnce deployments
- ClickOnce deployment, on-demand download
- on-demand assemblies, ClickOnce
ms.assetid: 59a0dd5f-1cab-4f2f-b780-0ab7399905d5
caps.latest.revision: "18"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: b19f8759ecaa29ffda36660877bfc69acaa06375
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer"></a>İzlenecek yol: Tasarımcıyı Kullanarak ClickOnce Dağıtım API'si ile İsteğe Bağlı Derlemeleri İndirme
Varsayılan olarak, tüm derlemelerde bulunan bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamayı ilk kez çalıştırdığınızda uygulama yüklenir. Ancak, küçük bir kullanıcılar kümesi tarafından kullanılan uygulamanızın parçalarını olabilir. Bu durumda, yalnızca türlerinden birini oluşturduğunuzda bütünleştirilmiş kodu indirmek istediğiniz. Aşağıdaki örneklerde, belirli derlemeleri "isteğe bağlı" olarak işaretlemek gösterilmiştir ve bunları kullanarak indirmek nasıl sınıfları <xref:System.Deployment.Application> ortak dil çalışma zamanı bunları talep ettiğinde ad alanı.  
  
> [!NOTE]
>  Uygulamanız bu yordamı kullanmak için tam güvende çalıştırmanız gerekir.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tıklatın. **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="creating-the-projects"></a>Proje oluşturma  
  
#### <a name="to-create-a-project-that-uses-an-on-demand-assembly-with-visual-studio"></a>Visual Studio ile isteğe bağlı bütünleştirilmiş kullanan bir proje oluşturmak için  
  
1.  Yeni bir Windows Forms projesi oluşturun [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Üzerinde **dosya** menüsündeki **Ekle**ve ardından **yeni proje**. Seçin bir **sınıf kitaplığı** projesi iletişim kutusunda ve adlandırın `ClickOnceLibrary`.  
  
    > [!NOTE]
    >  Visual Basic'te, bu proje için kök ad alanı değiştirmek için proje özelliklerini değiştirme olan öneririz `Microsoft.Samples.ClickOnceOnDemand` veya tercih ettiğiniz bir ad alanı. Kolaylık olması için bu kılavuzda iki proje aynı ad alanında ' dir.  
  
2.  Adlı bir sınıf tanımlama `DynamicClass` adlı tek bir özellik ile `Message`.  
  
     [!code-vb[ClickOnceLibrary#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_1.vb)]
     [!code-csharp[ClickOnceLibrary#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_1.cs)]  
  
3.  Windows Forms projedeki seçin **Çözüm Gezgini**. Bir başvuru ekleyin <xref:System.Deployment.Application> derleme ve bir proje başvurusu `ClickOnceLibrary` projesi.  
  
    > [!NOTE]
    >  Visual Basic'te, bu proje için kök ad alanı değiştirmek için proje özelliklerini değiştirme olan öneririz `Microsoft.Samples.ClickOnceOnDemand` veya tercih ettiğiniz bir ad alanı. Kolaylık olması için bu kılavuzda iki proje aynı ad alanında yer alır.  
  
4.  Forma sağ tıklayın, **görünümü kodu** menüsünde ve forma aşağıdaki başvurular ekleyin.  
  
     [!code-csharp[ClickOnceOnDemand#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_2.cs)]
     [!code-vb[ClickOnceOnDemand#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_2.vb)]  
  
5.  İsteğe bağlı Bu derlemeyi yüklemek için aşağıdaki kodu ekleyin. Bu kodu nasıl genel kullanarak bir grup adına derlemeler kümesini eşleneceğini gösterir <xref:System.Collections.DictionaryBase.Dictionary%2A> sınıfı. Biz yalnızca bu kılavuzda tek bir derleme indirme olmadığından bizim grubunda yalnızca bir derleme yoktur. Gerçek bir uygulamada büyük olasılıkla uygulamanız aynı anda tek bir özellik ilgili tüm derlemeleri indirmek istersiniz. Eşleme tablosu, kolayca indirme grubu adı ile bir özelliğe ait olan tüm DLL'leri ilişkilendirerek bunu yapmanızı sağlar.  
  
     [!code-csharp[ClickOnceOnDemand#2](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_3.cs)]
     [!code-vb[ClickOnceOnDemand#2](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_3.vb)]  
  
6.  Üzerinde **Görünüm** menüsünde tıklatın **araç**. Sürükleme bir <xref:System.Windows.Forms.Button> gelen **araç** forma. Düğmesine çift tıklayın ve aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> olay işleyicisi.  
  
     [!code-csharp[ClickOnceOnDemand#3](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_4.cs)]
     [!code-vb[ClickOnceOnDemand#3](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_4.vb)]  
  
## <a name="marking-assemblies-as-optional"></a>Derlemeleri isteğe bağlı olarak işaretleme  
  
#### <a name="to-mark-assemblies-as-optional-in-your-clickonce-application-by-using-visual-studio"></a>Visual Studio kullanarak derlemeleri ClickOnce uygulamanızda isteğe bağlı olarak işaretlemek için  
  
1.  Windows Forms projeye sağ **Çözüm Gezgini** tıklatıp **özellikleri**. Seçin **Yayımla** sekmesi.  
  
2.  Tıklatın **uygulama dosyalarını** düğmesi.  
  
3.  ClickOnceLibrary.dll için bulun. Ayarlama **yayımlama durumu** açılan kutusu **INCLUDE**.  
  
4.  Genişletme **grup** açılan kutusu ve select **yeni**. Bir ad girin `ClickOnceLibrary` yeni grup adı.  
  
5.  Bölümünde açıklandığı gibi uygulamanızı yayımlamaya devam [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
#### <a name="to-mark-assemblies-as-optional-in-your-clickonce-application-by-using-manifest-generation-and-editing-tool--graphical-client-mageuiexe"></a>Bildirim oluşturma ve düzenleme aracı kullanarak derlemeleri ClickOnce uygulamanızda isteğe bağlı olarak işaretlemek için — grafik istemcisi (MageUI.exe)  
  
1.  Oluştur, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] açıklandığı gibi bildirimleri [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
2.  MageUI.exe kapatmadan önce dağıtımınızın uygulama bildirimini içeren sekmeyi seçin ve bu sekmede seçin **dosyaları** sekmesi.  
  
3.  Uygulama dosyaları listesinde ClickOnceLibrary.dll'i bulun ve ayarlayın, **dosya türü** sütuna **hiçbiri**. İçin **grup** sütun, türü `ClickOnceLibrary.dll`.  
  
## <a name="testing-the-new-assembly"></a>Yeni bir derleme test etme  
  
#### <a name="to-test-your-on-demand-assembly"></a>İsteğe bağlı derlemenizi sınamak için  
  
1.  İle dağıtılan uygulamanızı başlatın [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
2.  Ana form görüntülendiğinde basın <xref:System.Windows.Forms.Button>. Dize, "Hello, World!" okuyan bir ileti kutusu penceresinde görmeniz gerekir  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Deployment.Application.ApplicationDeployment>