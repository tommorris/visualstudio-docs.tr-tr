---
title: Hizmet Başvurularında Sorun Giderme
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- msvse_wcf.Err.ReferenceGroup_NamespaceConflictsOther
- msvse_wcf.Err.AddSvcRefDlg_NothingSelectedOnGo
- msvse_wcf.Err.ErrorOnOK
- msvse_wcf.cfg.ConfigurationErrorsException
helpviewer_keywords:
- service references [Visual Studio], troubleshooting
- WCF services, troubleshooting
ms.assetid: 3b531120-1325-4734-90c6-6e6113bd12ac
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5e515c07d96bf959302b4499358c59bba5962b0c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="troubleshoot-service-references"></a>Hizmet başvuruları sorun giderme

Bu konuda, Windows Communication Foundation (WCF) veya Visual Studio'da WCF Veri Hizmetleri başvuruları ile çalışırken oluşabilecek yaygın sorunlar listelenmiştir.

## <a name="error-returning-data-from-a-service"></a>Bir hizmetinden veri döndürme hatası

Döndüğünüzde bir `DataSet` veya `DataTable` bir hizmetinden bir "gelen iletiler için en büyük boyutu kotası aşıldı" özel alabilirsiniz. Varsayılan olarak, `MaxReceivedMessageSize` özelliği bazı bağlamaları için hizmet reddi saldırılarına maruz sınırlamak için görece küçük bir değere ayarlanır. Özel durum önlemek için bu değeri artırabilirsiniz. Daha fazla bilgi için bkz. <xref:System.ServiceModel.HttpBindingBase.MaxReceivedMessageSize%2A>.

Bu hatayı düzeltmek için:

1.  İçinde **Çözüm Gezgini**, açmak için app.config dosyasına çift tıklayın.

2.  Bulun `MaxReceivedMessageSize` özellik ve daha büyük bir değerle değiştirin.

## <a name="cannot-find-a-service-in-my-solution"></a>Bir hizmet Çözümümde bulunamıyor

Tıkladığınızda **bulma** düğmesini **hizmeti başvuruları ekleme** iletişim kutusu, çözüm bir veya daha fazla WCF Hizmeti Kitaplığı projelerinde Hizmetler listesinde görünmez. Bir hizmet kitaplığı çözüme eklendi ancak henüz derlenmiş bu durum ortaya çıkabilir.

Bu hatayı düzeltmek için:

-   İçinde **Çözüm Gezgini**, WCF Hizmeti kitaplığı projeyi sağ tıklatın ve **yapı**.

## <a name="error-accessing-a-service-over-a-remote-desktop"></a>Uzak Masaüstü üzerinden bir hizmet erişilirken hata oluştu

Bir kullanıcı eriştiğinde, bir Web barındırılan bir WCF hizmeti üzerinden bir Uzak Masaüstü Bağlantısı ve kullanıcı yönetici izinlerine sahip değilse, NTLM kimlik doğrulaması kullanılır. Kullanıcı, kullanıcı yönetim izinlerine sahip değilse, aşağıdaki hata iletisini alabilirsiniz: "istemci kimlik doğrulama şeması 'Anonymous' HTTP isteği yetkilendirilmemiş. Sunucudan alınan kimlik doğrulama üstbilgisi 'NTLM' idi."

Bu hatayı düzeltmek için:

1.  Web sitesi projeyi açın **özellikleri** sayfaları.

2.  Üzerinde **başlangıç seçenekleri** sekmesi, Temizle **NTLM kimlik doğrulaması** onay kutusu.

    > [!NOTE]
    > NTLM kimlik doğrulaması yalnızca özel olarak WCF hizmetlerini içeren Web siteleri için kapatmanız. WCF hizmetleri için güvenlik web.config dosyasındaki yapılandırma yoluyla yönetilir. Bu, NTLM kimlik doğrulaması gereksiz kılar.

## <a name="access-level-for-generated-classes-setting-has-no-effect"></a>Oluşturulan sınıflar için erişim düzeyi ayarının hiçbir etkisi

Ayarı **erişim düzeyi oluşturulan sınıflar için** seçeneğini **Yapılandırma hizmeti başvuruları** iletişim kutusuna **dahili** veya **arkadaş** her zaman çalışmayabilir. Seçeneği iletişim kutusunda ayarlanacak görünse bile, sonuçta elde edilen destek sınıfları erişim düzeyi ile oluşturulan `Public`.

Bu bilinen olanlar kullanılarak serileştirilmiş gibi belirli türde bir kısıtlamadır <xref:System.Xml.Serialization.XmlSerializer>.

## <a name="error-debugging-service-code"></a>Hata hata ayıklama hizmet kodu

İstemci koddan bir WCF hizmeti için koda adım, eksik simgeleri ilgili bir hata alabilirsiniz. Çözümünüzü parçası olan bir hizmeti taşınmış veya çözümden kaldırıldığında bu durum oluşabilir.

İlk kez geçerli çözümünün bir parçası olan bir WCF hizmetine başvuru eklediğinizde, açık derleme bağımlılığına hizmet projesi ve hizmeti istemci projesi arasında eklenir. Bu, istemci her zaman güncel hizmeti ikili dosyalarını, istemci kodu hizmet koda atlama gibi senaryolar hata ayıklama için özellikle önemli olduğu erişme garanti eder.

Hizmet projesinin çözümden kaldırılırsa, bu açık derleme bağımlılığı geçersiz kılınır. Visual Studio artık hizmeti projesi yapılana gerektiğinde garanti edebilir.

Bu hatayı düzeltmek için el ile hizmet projeyi yeniden vardır:

1.  Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.

2.  İçinde **seçenekleri** iletişim kutusunda, genişletin **projeler ve çözümler**ve ardından **genel**.

3.  Olduğundan emin olun **Göster Gelişmiş derleme yapılandırmaları** onay kutusu seçilidir ve ardından **Tamam**.

4.  WCF hizmet projesi yükleyin.

5.  İçinde **Configuration Manager** iletişim kutusu, kümesi **etkin çözüm yapılandırması** için **hata ayıklama**. Daha fazla bilgi için bkz: [nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../ide/how-to-create-and-edit-configurations.md).

6.  İçinde **Çözüm Gezgini**, WCF Hizmeti projesini seçin.

7.  Üzerinde **yapı** menüsünde tıklatın **yeniden** WCF Hizmeti projeyi oluşturmak için.

## <a name="wcf-data-services-do-not-display-in-the-browser"></a>WCF Veri Hizmetleri tarayıcıda görüntüleme

Ne zaman çalışır bir XML temsili verileri görüntülemek bir [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)], Internet Explorer verileri bir RSS akışı olarak hatalı yorumlayan. RSS akışları görüntüleme seçeneği devre dışı bırakıldığından emin olun.

Bu hatayı düzeltmek için RSS akışları devre dışı bırakın:

1.  Internet Explorer'da, üzerinde **Araçları** menüsünde tıklatın **Internet Seçenekleri**.

2.  Üzerinde **içerik** sekmesinde **akışları** 'yi tıklatın **ayarları**.

3.  İçinde **akış ayarları** iletişim kutusu, Temizle **akış üzerinde Okuma Görünümü Aç** onay kutusunu işaretleyin ve ardından **Tamam**.

4.  Tıklatın **Tamam** kapatmak için **Internet Seçenekleri** iletişim kutusu.

## <a name="see-also"></a>Ayrıca Bkz.

- [Windows Communication Foundation Hizmetleri ve Visual Studio'da WCF Veri Hizmetleri](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)