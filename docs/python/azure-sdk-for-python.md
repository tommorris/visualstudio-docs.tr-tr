---
title: Python için Azure SDK
description: Python için Azure SDK'sı, Microsoft Azure hizmetlerini herhangi bir platformda çalışan Python uygulamalardan kullanma kolaylaştırır.
ms.date: 01/22/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 58e7f6cd46293573f17c344ffba943d99b55f830
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
ms.locfileid: "32031478"
---
# <a name="azure-sdk-for-python"></a>Python için Azure SDK

Python için Azure SDK'sını kullanabilir ve Windows, Mac OSX ve Linux üzerinde çalışan uygulamalardan Microsoft Azure hizmetlerini yönetmek kolaylaştırır.

## <a name="installation"></a>Yükleme

Azure SDK'sını gelen yüklü [Python paket dizini](https://pypi.python.org/pypi/azure).

Yükleme **en yeni kararlı sürüm** (gibi Python 2.7 ve 3.x destekler):

```command
pip install azure
```

Ayrıca izleyebilirsiniz [Python yüklemek ve SDK](https://docs.microsoft.com/azure/python-how-to-install/) Azure belgelerinde.

## <a name="documentation"></a>Belgeler

Belge üzerinde bulunabilir [python.readthedocs.org için azure sdk](https://docs.microsoft.com/en-us/python/azure/?view=azure-python).

[Python Geliştirici Merkezi için Azure SDK](http://azure.microsoft.com/develop/python/) de yararlı kaynaklara öğreticileri sayısı dahil olmak üzere, çeşitli vardır:

- Web uygulamaları ile oluşturma [Django](/azure/app-service-web/web-sites-python-create-deploy-django-app) [Flask](/azure/app-service-web/web-sites-python-create-deploy-flask-app), ve [Bottle](/azure/app-service-web/web-sites-python-create-deploy-bottle-app).
- [BLOB Depolama](/azure/storage/storage-python-how-to-use-blob-storage)
- [Tablo depolama](/azure/storage/storage-python-how-to-use-table-storage)
- [Kuyruk depolama](/azure/storage/storage-python-how-to-use-queue-storage)
- [Azure Cosmos DB](/azure/cosmos-db/sql-api-python-application)
- [Service Bus kuyrukları](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
- [Hizmet veri yolu konuları/abonelikleri](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [Hizmet Yönetimi](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Belgeler olmadan ortak API'ler için birim testleri içinde [SDK GitHub deposunu](https://github.com/Azure/azure-sdk-for-python) iyi bilgi kaynağıdır:

- [Birim testleri](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Hizmet veri yolu birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Hizmet Yönetimi birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)
- [Kaynak Yönetimi birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-mgmt/tests)

## <a name="support"></a>Destek

SDK'sı için Git deposu adresindedir [ https://github.com/Azure/azure-sdk-for-python ](https://github.com/Azure/azure-sdk-for-python).

[Depo sorunları dosya](https://github.com/Azure/azure-sdk-for-python/issues) sorunları bulmak ya da SDK'ın kullanımıyla ilgili sorularınız varsa.
