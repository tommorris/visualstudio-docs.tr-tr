---
title: 'İzlenecek yol: Başlangıç sayfasına özel XAML ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom start page
- xaml start page
ms.assetid: 9af4d5f9-1cfc-4221-aea7-c8cd3f7571a6
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 796beda7675d45698dd361e09f5b27e54d8b5da6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696000"
---
# <a name="walkthrough-adding-custom-xaml-to-the-start-page"></a>İzlenecek Yol: Başlangıç Sayfasına Özel XAML Ekleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [izlenecek yol: başlangıç sayfasına özel XAML ekleme](https://docs.microsoft.com/visualstudio/extensibility/walkthrough-adding-custom-xaml-to-the-start-page).  
  
Bu kılavuzda, özel bir Visual Studio Başlangıç içeren bir Web tarayıcısı sayfası oluşturma işlemi gösterilmektedir.  
  
## <a name="adding-custom-xaml"></a>Özel XAML ekleme  
  
1.  Bir başlangıç sayfası'ndaki yönergeleri takip ederek oluşturma [bir özel başlangıç sayfası oluşturma](../extensibility/creating-a-custom-start-page.md).  
  
2.  MainWindow.xaml dosyasını bulun \<kılavuz > bölümü.  
  
3.  Ekleme bir \<TabControl > öğesi ve bir \<TabItem > içinde \< kılavuz > öğesi, aşağıdaki örnekte gösterildiği gibi.  
  
    ```xml  
    <Grid>  
        <TabControl>  
            <TabItem Header="Bing" Height="Auto">  
                <Frame Source="http://www.bing.com" />  
            </TabItem>  
        </TabControl>  
    </Grid>  
    ```  
  
4.  İkinci bir ekleme \<TabItem >, ile bir \<düğmesi > Yeni bir proje açılır öğe:  
  
    ```xml  
    <Grid>  
        <TabControl>  
            <TabItem Header="MyButton" Height="Auto">  
                <Button Name="btnNewProj" Content="New Project"   
                    Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
                    CommandParameter="File.NewProject" >  
                </Button>  
            </TabItem>  
            <TabItem Header="Bing" Height="Auto">  
                <Frame Source="http://www.bing.com" />  
            </TabItem>  
        </TabControl>  
    </Grid>  
    ```  
  
## <a name="testing-the-custom-start-page"></a>Özel başlangıç sayfasını test etme  
  
1.  F5 tuşuna basın.  
  
     Visual Studio'nun deneysel örneğinde, özel başlangıç yüklendi, ancak seçili sayfası ile açılır.  
  
2.  Visual Studio'nun deneysel örneğinde açın **araçları/Options / ortam** sayfası.  
  
3.  Seçin **başlangıç**. Üzerinde **başlangıç sayfasını Özelleştir** listesinde, .xaml dosyanızı seçin ve tıklayın **Tamam**.  
  
4.  Üzerinde **görünümü** menüsünü tıklatın **başlangıç sayfası**.  
  
5.  Tıklayın **Bing** sekmesi.  
  
     Bing web sayfası görmeniz gerekir.  
  
6.  Tıklayın **MyButton** sekmesi.  
  
     Görmelisiniz bir **MyProject** düğmesini açan **yeni proje** iletişim.  
  
7.  Deneysel örneği kapatın.  
  
## <a name="applying-the-custom-start-page"></a>Özel başlangıç sayfası uygulama  
  
#### <a name="to-test-the-custom-start-page"></a>Özel başlangıç sayfası test etmek için  
  
1.  İçinde **Araçlar / Seçenekler / ortam**seçin **başlangıç**. Üzerinde **başlangıç sayfasını Özelleştir** listesinde, .xaml dosyanızı seçin ve tıklayın **Tamam**.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Visual Studio Başlangıç sayfası artık bir Web tarayıcısı sekmesi ve MyButton sekme görüntüleyen bir sekme içerir. Özel başlangıç diğer işlevleri kullanarak olan sayfaları oluşturabilirsiniz *arka plan kod* gösterildiği gibi özel bir .dll dosyasını eklemek için model [başlangıç sayfasına kullanıcı denetimi ekleme](../extensibility/adding-user-control-to-the-start-page.md). Özel başlangıç sayfaları için elde edilen .vsix dosyasını yayımlayarak diğer kullanıcılarla paylaşabilir miyim [Visual Studio Galerisi](http://go.microsoft.com/fwlink/?LinkID=123847) Web sitesini veya başka bir Web sitesinin veya ağ paylaşımı. Daha fazla bilgi için [özel başlangıç sayfaları dağıtma](../extensibility/deploying-custom-start-pages.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlangıç sayfasını özelleştirme](../ide/customizing-the-start-page-for-visual-studio.md)   
 [WPF kapsayıcı denetimleri](http://msdn.microsoft.com/en-us/a0177167-d7db-4205-9607-8ae316952566)

