---
title: "İzlenecek yol: Özel XAML başlangıç sayfasına ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom start page
- xaml start page
ms.assetid: 9af4d5f9-1cfc-4221-aea7-c8cd3f7571a6
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 65875823e2bc6e09eb0439a267a9c25acada87fa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-adding-custom-xaml-to-the-start-page"></a>İzlenecek yol: Özel XAML başlangıç sayfasına ekleme
Bu izlenecek özel Visual Studio Başlangıç içeren bir Web tarayıcısı sayfası oluşturulacağını gösterir.  
  
## <a name="adding-custom-xaml"></a>Özel XAML ekleme  
  
1.  Bir başlangıç sayfası'ndaki yönergeleri izleyerek oluşturun [bir özel başlangıç sayfası oluşturma](../extensibility/creating-a-custom-start-page.md).  
  
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
  
     Visual Studio'nun deneysel örneği, özel başlangıç yüklendi, ancak seçili sayfası ile açılır.  
  
2.  Visual Studio deneysel örneği açın **Araçlar/Options / ortamı** sayfası.  
  
3.  Seçin **başlangıç**. Üzerinde **başlangıç sayfasını özelleştirme** listesinde, .xaml dosyasında seçin ve tıklatın **Tamam**.  
  
4.  Üzerinde **Görünüm** menüsünde tıklatın **başlangıç sayfası**.  
  
5.  Tıklatın **Bing** sekmesi.  
  
     Bing web sayfasını görmeniz gerekir.  
  
6.  Tıklatın **MyButton** sekmesi.  
  
     Görmeniz gerekir bir **MyProject** button, açan **yeni proje** iletişim.  
  
7.  Deneysel örneği kapatın.  
  
## <a name="applying-the-custom-start-page"></a>Özel başlangıç sayfası uygulama  
  
#### <a name="to-test-the-custom-start-page"></a>Özel başlangıç sayfası test etmek için  
  
1.  İçinde **Araçlar / Seçenekler / ortamı**seçin **başlangıç**. Üzerinde **başlangıç sayfasını özelleştirme** listesinde, .xaml dosyasında seçin ve tıklatın **Tamam**.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Visual Studio Başlangıç sayfası artık bir Web tarayıcısı sekmesi ve MyButton sekmesini görüntüler bir sekme içerir. Özel başlangıç diğer işlevleri kullanarak olan sayfaları oluşturabilirsiniz *arka plan kodu* gösterildiği gibi özel bir .dll eklemek için model [kullanıcı denetimine ekleme başlangıç sayfası](../extensibility/adding-user-control-to-the-start-page.md). Özel başlangıç sayfaları sonuçta elde edilen .vsix dosyasına yayımlayarak diğer kullanıcılarla paylaşmak [Visual Studio Galerisi](http://go.microsoft.com/fwlink/?LinkID=123847) Web sitesini veya başka bir Web sitesi ya da ağ paylaşır. Daha fazla bilgi için bkz: [dağıtma özel başlangıç sayfaları](../extensibility/deploying-custom-start-pages.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlangıç sayfasını özelleştirme](../ide/customizing-the-start-page-for-visual-studio.md)   
 [WPF kapsayıcı denetimleri](http://msdn.microsoft.com/en-us/a0177167-d7db-4205-9607-8ae316952566)