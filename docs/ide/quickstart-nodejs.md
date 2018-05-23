---
title: 'Hızlı Başlangıç: Kullanım ilk Node.js uygulamanızı oluşturmak için Visual Studio'
description: Bu hızlı başlangıç Visual Studio'da bir Node.js uygulaması oluşturma
ms.date: 11/15/2017
ms.prod: visual-studio-dev15
ms.technology: vs-nodejs
ms.topic: quickstart
ms.devlang: javascript
ms.assetid: b0e4ebed-1a01-41ef-aad1-4d8465ce5322
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 0a78f9fdfd1ea3612d86432619c463d526eed5c2
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
---
# <a name="quickstart-use-visual-studio-to-create-your-first-nodejs-app"></a>Hızlı Başlangıç: Kullanım ilk Node.js uygulamanızı oluşturmak için Visual Studio

Bu 5-10 dakikalık bir giriş Visual Studio tümleşik geliştirme ortamı (IDE), basit bir Node.js web uygulaması oluşturacaksınız. Visual Studio 2017 henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) ücretsiz yüklemek için sayfa.

## <a name="create-a-project"></a>Proje oluşturma
İlk olarak, bir Node.js web uygulaması projesi oluşturacaksınız.

1. Zaten yüklü Node.js çalışma zamanı yoksa, LTS sürümünden yükleme [Node.js](https://nodejs.org/en/download/) Web sitesi.

    Genel olarak, Visual Studio yüklenmiş Node.js çalışma zamanı otomatik olarak algılar. Yüklü bir çalışma zamanı algılamazsa yüklü çalışma zamanı özellikleri sayfasında başvurmak için projenizi yapılandırabilirsiniz (bir proje oluşturduktan sonra proje düğümüne sağ tıklayın ve seçin **özellikleri**).

1. Visual Studio 2017'ni açın.

1. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje**.

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, genişletin **JavaScript**, ardından **Node.js**. Orta bölmede seçin **boş Node.js Web uygulaması**, ardından **Tamam**.

     Görmüyorsanız, **boş Node.js Web uygulaması** proje şablonu, tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Seçin **Node.js geliştirme** iş yükü, ardından **Değiştir**.

     ![VS yükleyici node.js iş yükü](../ide/media/quickstart-nodejs-workload.png)

    Visual Studio oluşturur ve yeni bir çözüm ve proje açar. *Server.js* sol bölmede Düzenleyicisi'nde açar.

## <a name="explore-the-ide"></a>IDE keşfedin

1. Bir göz atalım **Çözüm Gezgini** sağ bölmede.

   ![Çözüm Gezgini](../ide/media/quickstart-nodejs-solution-explorer.png)

  - Kalın olarak vurgulanmış olan, vermiş adını kullanarak projenize **yeni proje** iletişim kutusu. Diskte, bu proje tarafından temsil edilen bir *.njsproj* proje klasörünüzdeki dosya.

  - En üst düzeyinde varsayılan olarak, projenizin aynı ada sahip bir, çözümüdür. Tarafından temsil edilen bir çözüm bir *.sln* dosya diskte, bir veya daha fazla ilgili projeleri için bir kapsayıcıdır.

  - Npm düğüm herhangi bir yüklü npm paket gösterir. Arayın ve iletişim kutusunu kullanarak npm paket yüklemek için npm düğümünü sağ tıklayabilirsiniz.

1. Npm paket veya node.js komutlar bir komut isteminden yüklemek istiyorsanız, proje düğümüne sağ tıklayın ve seçin **burada açık bir komut istemi**.

   ![Node.js komut istemi](../ide/media/quickstart-nodejs-command-prompt.png)

1. İçinde *server.js* dosya Düzenleyicisi (sol bölme), seçin `http.createServer` ve tuşuna basarak **F12** veya seçin **Tanıma Git** (sağ tıklatma) bağlam menüsünden. Bu komut tanımına alır `createServer` işlevi *index.d.ts*.

   ![Tanıma Git bağlam menüsü](../ide/media/quickstart-nodejs-gotodefinition.png)

1. İçin geri alındı *server.js*, ardından imleci dizesi sonunda kodu, bu satırda alın `res.end('Hello World\n');`ve şuna benzer şekilde değiştirin:

    `res.end('Hello World\n' + res.connection.`

    Girebileceğiniz `connection.`, IntelliSense kod girişini otomatik olarak tamamlamak için seçenekler sağlar.

   ![IntelliSense otomatik tamamlama](../ide/media/quickstart-nodejs-intellisense.png)

1. Seçin **yerel bağlantı noktası**ve ardından `);` şuna benzer şekilde, deyim tamamlamak için:

    `res.end('Hello World\n' + res.connection.localPort);`

## <a name="run-the-application"></a>Uygulamayı çalıştırın

1. Tuşuna **Ctrl**+**F5** (veya **hata ayıklama > hata ayıklama olmadan Başlat**) uygulamayı çalıştırın. Uygulamayı tarayıcıda açılır.

1. Tarayıcı penceresinde "Hello World" artı yerel bağlantı noktası numarasını görürsünüz.

1. Web tarayıcısını kapatın.

Bu hızlı başlangıç Tamamlanıyor Tebrikler! Visual Studio IDE hakkında biraz öğrenilen umuyoruz. Lütfen yeteneklerini daha derin inceleyin istiyorsanız bir öğreticide devam **öğreticileri** içindekiler bölümü.

## <a name="next-steps"></a>Sonraki adımlar

- Git üzerinden [Node.js ve Express için Öğreticisi](../nodejs/tutorial-nodejs.md)
- Git üzerinden [Node.js ve tepki göstermek için Öğreticisi](../nodejs/tutorial-nodejs-with-react-and-jsx.md)