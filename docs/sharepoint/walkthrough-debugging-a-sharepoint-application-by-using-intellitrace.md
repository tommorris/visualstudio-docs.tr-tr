---
title: "İzlenecek yol: IntelliTrace'i kullanarak SharePoint uygulama hata ayıklama | Microsoft Docs"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- IntelliTrace [SharePoint development in Visual Studio]
- standalone data collector
- SharePoint development in Visual Studio, IntelliTrace
- data collector
- IntelliTrace
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 173dbc74a24166f69ca97da6d5f68332345b90ea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-debugging-a-sharepoint-application-by-using-intellitrace"></a>İzlenecek yol: IntelliTrace'i Kullanarak SharePoint Uygulamasında Hata Ayıklama

IntelliTrace'i kullanarak SharePoint çözümleri daha kolay ayıklayabilirsiniz. Geleneksel hata ayıklayıcıları geçerli şu anda yalnızca bir anlık görüntüsü bir çözümün verin. Ancak, IntelliTrace çözümünüzde oluştu geçmiş olaylar ve içerik, bunlar oluştu ve koda gidin gözden geçirmek için kullanabilirsiniz.

 Bu kılavuz, dağıtılan uygulamalarından IntelliTrace verilerini toplamak için Microsoft Monitoring Agent'ı kullanarak bir SharePoint 2010 veya SharePoint 2013 proje Visual Studio'da hata ayıklama gösterilmiştir. Bu verileri çözümlemek için Visual Studio Enterprise kullanmanız gerekir. Bu proje özelliği etkinleştirildiğinde, görev listesi ve duyuru Duyurular listesi için bir görev ekler ve bir özellik alıcısı içerir. Özelliği devre dışı bırakıldığında görev tamamlandı olarak işaretlenir ve ikinci bir duyuru Duyurular listesine eklenir. Ancak, yordam projeyi düzgün çalışmasını engelleyen mantıksal bir hata içeriyor. IntelliTrace'i kullanarak bulun ve hatayı düzeltin.

 **Uygulandığı öğe:** bu konudaki bilgiler, Visual Studio'da oluşturulan SharePoint 2010 ve SharePoint 2013 çözümleri için geçerlidir.

 Bu izlenecek yol aşağıdaki görevleri gösterir:

- [Özellik alıcısı oluşturma](#BKMK_CreateReceiver)

- [Özellik alıcısı için kod ekleme](#BKMK_AddCode)

- [Projeyi test](#BKMK_Test1)

- [Microsoft Monitoring Agent'ı kullanarak IntelliTrace verilerini toplama](#BKMK_CollectDiagnosticData)

- [Hata ayıklama ve SharePoint çözüm Düzelt](#BKMK_DebugSolution)

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

- Windows ve SharePoint sürümleri desteklenir. Bkz: [SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

- Visual Studio Enterprise.

## <a name="BKMK_CreateReceiver"></a> Özellik alıcısı oluşturma

İlk olarak bir özellik alıcısı sahip boş bir SharePoint projesi oluşturun.

1. SharePoint 2010 veya SharePoint 2013 çözüm projesi oluşturun ve adlandırın **IntelliTraceTest**.

     **SharePoint Özelleştirme Sihirbazı'nı** , hem SharePoint sitesi, proje ve çözüm güven düzeyini için belirtebileceğiniz görüntülenir.

2. Seçin **Grup çözümü olarak dağıtma** seçenek düğmesine ve ardından **son** düğmesi.

     IntelliTrace yalnızca küme çözümleri üzerinde çalışır.

3. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **özellikleri** düğümünü ve ardından **Özellik Ekle**.

     Feature1.Feature görünür.

4. Feature1.feature için kısayol menüsünü açın ve ardından **olay alıcısı Ekle** bir kod modülüne özelliği eklemek için.

## <a name="BKMK_AddCode"></a> Özellik alıcısı için kod ekleme

Ardından, özellik alıcısı öğesinde iki yöntem için kodu ekleyin: `FeatureActivated` ve `FeatureDeactivating`. Bu yöntemlerin her bir özelliği etkinleştirilmiş veya SharePoint'te sırasıyla devre dışı tetikler.

1. Üstündeki `Feature1EventReceiver` sınıfı, SharePoint site ve alt belirtin değişkenler bildirilmektedir aşağıdaki kodu ekleyin:

    ```vb
    ' SharePoint site and subsite.
    Private siteUrl As String = "http://localhost"
    Private webUrl As String = "/"
    ```

    ```csharp
    // SharePoint site and subsite.
    private string siteUrl = "http://localhost";
    private string webUrl = "/";
    ```

2. Değiştir `FeatureActivated` aşağıdaki kod ile yöntemi:

    ```vb
    Public Overrides Sub FeatureActivated(ByVal properties As SPFeatureReceiverProperties)
        Try
            Using site As New SPSite(siteUrl)
                Using web As SPWeb = site.OpenWeb(webUrl)
                    ' Reference the lists.
                    Dim announcementsList As SPList = web.Lists("Announcements")
                    Dim taskList As SPList = web.Lists("Tasks")

                    ' Add an announcement to the Announcements list.
                    Dim listItem As SPListItem = announcementsList.Items.Add()
                    listItem("Title") = "Activated Feature: " & Convert.ToString(properties.Definition.DisplayName)
                    listItem("Body") = Convert.ToString(properties.Definition.DisplayName) & " was activated on: " & DateTime.Now.ToString()
                    listItem.Update()

                    ' Add a task to the Task list.
                    Dim newTask As SPListItem = taskList.Items.Add()
                    newTask("Title") = "Deactivate feature: " & Convert.ToString(properties.Definition.DisplayName)
                    newTask.Update()
                End Using
            End Using

        Catch e As Exception
            Console.WriteLine("Error: " & e.ToString())
        End Try

    End Sub
    ```

    ```csharp
    public override void FeatureActivated(SPFeatureReceiverProperties properties)
    {
        try
        {
            using (SPSite site = new SPSite(siteUrl))
            {
                using (SPWeb web = site.OpenWeb(webUrl))
                {
                    // Reference the lists.
                    SPList announcementsList = web.Lists["Announcements"];
                    SPList taskList = web.Lists["Tasks"];

                    // Add an announcement to the Announcements list.
                    SPListItem listItem = announcementsList.Items.Add();
                    listItem["Title"] = "Activated Feature: " + properties.Definition.DisplayName;
                    listItem["Body"] = properties.Definition.DisplayName + " was activated on: " + DateTime.Now.ToString();
                    listItem.Update();

                    // Add a task to the Task list.
                    SPListItem newTask = taskList.Items.Add();
                    newTask["Title"] = "Deactivate feature: " + properties.Definition.DisplayName;
                    newTask.Update();
                }
            }
        }

        catch (Exception e)
        {
            Console.WriteLine("Error: " + e.ToString());
        }

    }
    ```

3. Değiştir `FeatureDeactivating` aşağıdaki kod ile yöntemi:

    ```vb
    Public Overrides Sub FeatureDeactivating(ByVal properties As SPFeatureReceiverProperties)
        ' The following line induces an error to demonstrate debugging.
        ' Remove this line later for proper operation.
        Throw New System.InvalidOperationException("Serious error occurred!")
        Try
            Using site As New SPSite(siteUrl)
                Using web As SPWeb = site.OpenWeb(webUrl)
                    ' Reference the lists.
                    Dim taskList As SPList = web.Lists("Tasks")
                    Dim announcementsList As SPList = web.Lists("Announcements")

                    ' Add an announcement that the feature was deactivated.
                    Dim listItem As SPListItem = announcementsList.Items.Add()
                    listItem("Title") = "Deactivated Feature: " & Convert.ToString(properties.Definition.DisplayName)
                    listItem("Body") = Convert.ToString(properties.Definition.DisplayName) & " was deactivated on: " & DateTime.Now.ToString()
                    listItem.Update()

                    ' Find the task that the feature receiver added to the Task list when the
                    ' feature was activated.
                    Dim qry As New SPQuery()
                    qry.Query = "<Where><Contains><FieldRef Name='Title' /><Value Type='Text'>Deactivate</Value></Contains></Where>"
                    Dim taskItems As SPListItemCollection = taskList.GetItems(qry)

                    For Each taskItem As SPListItem In taskItems
                        ' Mark the task as complete.
                        taskItem("PercentComplete") = 1
                        taskItem("Status") = "Completed"
                        taskItem.Update()
                    Next
                End Using

            End Using

        Catch e As Exception
            Console.WriteLine("Error: " & e.ToString())
        End Try

    End Sub
    ```

    ```csharp
    public override void FeatureDeactivating(SPFeatureReceiverProperties properties)
    {
        // The following line induces an error to demonstrate debugging.
        // Remove this line later for proper operation.
        throw new System.InvalidOperationException("A serious error occurred!"); 
        try
        {
            using (SPSite site = new SPSite(siteUrl))
            {
                using (SPWeb web = site.OpenWeb(webUrl))
                {
                    // Reference the lists.
                    SPList taskList = web.Lists["Tasks"];
                    SPList announcementsList = web.Lists["Announcements"];

                    // Add an announcement that the feature was deactivated.
                    SPListItem listItem = announcementsList.Items.Add();
                    listItem["Title"] = "Deactivated Feature: " + properties.Definition.DisplayName;
                    listItem["Body"] = properties.Definition.DisplayName + " was deactivated on: " + DateTime.Now.ToString();
                    listItem.Update();

                    // Find the task that the feature receiver added to the Task list when the
                    // feature was activated.
                    SPQuery qry = new SPQuery();
                    qry.Query = "<Where><Contains><FieldRef Name='Title' /><Value Type='Text'>Deactivate</Value></Contains></Where>";
                    SPListItemCollection taskItems = taskList.GetItems(qry);

                    foreach (SPListItem taskItem in taskItems)
                    {
                        // Mark the task as complete.
                        taskItem["PercentComplete"] = 1;
                        taskItem["Status"] = "Completed";
                        taskItem.Update();
                    }
                }
            }

        }

        catch (Exception e)
        {
            Console.WriteLine("Error: " + e.ToString());
        }
    }
    ```

## <a name="BKMK_Test1"></a> Projeyi test

Özellik alıcısı kodu eklenir ve veri toplayıcısı çalışıyor göre dağıtın ve düzgün çalıştığını olup olmadığını sınamak için SharePoint çözüm çalıştırın.

> [!IMPORTANT]
> Bu örnekte, bir hata FeatureDeactivating olay işleyicisini atılır. Bu kılavuzda daha sonra bu hata, veri toplayıcı oluşturulan .iTrace dosyası kullanarak bulun.

1. Çözümü dağıtmak için SharePoint ve SharePoint sitesini bir tarayıcıda açın.

     Özellik otomatik olarak etkinleştirir, duyuru ve bir görev eklemek, özellik alıcısı neden olur.

2. Duyuruları ve görevleri listeler içeriğini görüntüleyebilir.

     Duyurular listesi adlı yeni bir duyuru olmalıdır **etkinleştirildi özellik: IntelliTraceTest_Feature1**, ve görev listesi adlı yeni bir görev içermelidir **devre dışı bırakma özelliği: IntelliTraceTest_ Feature1**. Bu öğelerden herhangi birini yoksa, özelliği etkin olup olmadığını doğrulayın. Etkin değilse, bunu etkinleştirin.

3. Özelliği aşağıdaki adımları uygulayarak devre dışı bırakın:

    1. Üzerinde **Site eylemleri** SharePoint menüde seçin **Site Ayarları**.

    2. Altında **Site eylemleri**, seçin **site özelliklerini Yönet** bağlantı.

    3. Yanına **IntelliTraceTest Feature1**, seçin **etkinliğini** düğmesi.

    4. Uyarı sayfasında, **bu özelliği devre dışı** bağlantı.

     FeatureDeactivating() olay işleyicisi bir hata oluşturur.

## <a name="BKMK_CollectDiagnosticData"></a> Microsoft Monitoring Agent'ı kullanarak IntelliTrace verilerini toplama

SharePoint çalıştıran sistemde Microsoft İzleme Aracısı yüklerseniz, IntelliTrace genel bilgileri daha fazla özel veriler kullanarak SharePoint çözümlerini ayıklayabilirsiniz. Aracı, SharePoint çözüm çalışmalarınız sırasında hata ayıklama bilgileri yakalamak için PowerShell cmdlet'lerini kullanarak Visual Studio dışında çalışır.

> [!NOTE]
> Bu örnek için bu bölümdeki yapılandırma bilgilerini özeldir. Diğer yapılandırma seçenekleri hakkında daha fazla bilgi için bkz: [IntelliTrace tek başına toplayıcıyı kullanma](/visualstudio/debugger/using-the-intellitrace-stand-alone-collector).

1. SharePoint çalıştıran bilgisayarda [Microsoft izleme aracısını ayarlama ve çözümünüzü izlemek başlangıç](/visualstudio/debugger/using-the-intellitrace-stand-alone-collector).

2. Özelliği devre dışı bırakın:

    1. Üzerinde **Site eylemleri** SharePoint menüde seçin **Site Ayarları**.

    2. Altında **Site eylemleri**, seçin **site özelliklerini Yönet** bağlantı.

    3. Yanına **IntelliTraceTest Feature1**, seçin **etkinliğini** düğmesi.

    4. Uyarı sayfasında, **bu özelliği devre dışı** bağlantı.

     (Bu durumda, FeatureDeactivating() olay işleyicisini durum hatası) nedeniyle bir hata oluşur.

3. PowerShell penceresinde çalıştırın [Stop-WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313687) SharePoint çözümünüzü yeniden .iTrace dosyası oluşturun ve izlemeyi durdurmak için komutu.

     **Stop-WebApplicationMonitoring***"\<SharePointSite >\\< SharePointAppName\>"*

## <a name="BKMK_DebugSolution"></a> Hata ayıklama ve SharePoint çözüm Düzelt

Artık bulmak ve SharePoint çözümde hatayı düzeltmek için Visual Studio IntelliTrace günlük dosyasını görüntüleyebilirsiniz.

1. \IntelliTraceLogs klasöründe, Visual Studio .iTrace dosyasını açın.

     **IntelliTrace Özet** sayfası görüntülenir. Hata işlenmemiş olduğundan SharePoint bağıntı kimliği (GUID) işlenmemiş özel durum alanında görünür **analiz** bölümü. Seçin **çağrı yığını** hatanın oluştuğu çağrı yığını görüntülemek istiyorsanız düğmesine tıklayın.

2. Seçin **hata ayıklama özel durum** düğmesi.

     İstenirse, simge dosyaları yükleyin. İçinde **IntelliTrace** özel durum penceresinde vurgulu olarak "sayıcı: önemli bir hata oluştu!".

     IntelliTrace penceresinde başarısız kodunu görüntülemek için özel durumu seçin.

3. SharePoint çözüm açılıyor ve sonra da çıkışı yorum oluşturma veya kaldırarak hatayı düzeltmek **throw** deyimini dosyanın üst FeatureDeactivating() yordamının.

4. Visual Studio çözümü yeniden derleyin ve SharePoint'e yeniden dağıtın.

5. Özelliği aşağıdaki adımları uygulayarak devre dışı bırakın:

    1. Üzerinde **Site eylemleri** SharePoint menüde seçin **Site Ayarları**.

    2. Altında **Site eylemleri**, seçin **site özelliklerini Yönet** bağlantı.

    3. Yanına **IntelliTraceTest Feature1**, seçin **etkinliğini** düğmesi.

    4. Uyarı sayfasında, **bu özelliği devre dışı** bağlantı.

6. Görev listesini açın ve doğrulayın **durum** devre dışı bırak görev değerini "tamamlandı" ve kendi **tamamlanma yüzdesi** değer % 100.

     Kod artık doğru şekilde çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[SharePoint Kodunu Doğrulama ve Hata Ayıklama](../sharepoint/verifying-and-debugging-sharepoint-code.md)  
[IntelliTrace](/visualstudio/debugger/intellitrace)  
[İzlenecek yol: Birim testleri kullanarak SharePoint kodunu doğrulayın.](https://msdn.microsoft.com/library/gg599006(v=vs.100).aspx)
