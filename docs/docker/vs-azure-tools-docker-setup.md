---
title: Bir Docker konağı yapılandırmak VirtualBox ile | Microsoft Docs
description: Docker makinesi ve VirtualBox kullanarak varsayılan Docker örneği yapılandırmak için adım adım yönergeler
services: azure-container-service
documentationcenter: na
author: mlearned
manager: douge
editor: ''
ms.assetid: 0b1335a2-7720-42a8-8260-4e06fc00c9f6
ms.service: multiple
ms.devlang: dotnet
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: multiple
ms.date: 06/08/2016
ms.author: mlearned
ms.openlocfilehash: 01b7d2a8fa0ea496966e9c19caf1dcfb9d29543f
ms.sourcegitcommit: 159ed9d4f56cdc1dff2fd19d9dffafe77e46cd4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2018
ms.locfileid: "53738167"
---
# <a name="configure-a-docker-host-with-virtualbox"></a>VirtualBox ile Docker Konağını Yapılandırma
## <a name="overview"></a>Genel Bakış
Bu makalede, Docker Machine ve VirtualBox kullanarak varsayılan Docker örneği yapılandırırken size kılavuzluk eder.
Kullanıyorsanız [için Docker Windows](https://www.docker.com/products/docker-desktop), bu yapılandırma gerekli değildir.

## <a name="prerequisites"></a>Önkoşullar
Aşağıdaki araçlar yüklü olması gerekir.

* [Docker araç kutusu](https://github.com/docker/toolbox/releases)

## <a name="configuring-the-docker-client-with-windows-powershell"></a>Windows PowerShell ile Docker İstemcisi'ni yapılandırma
Docker istemciyi yapılandırmak için yalnızca Windows PowerShell'i açın ve aşağıdaki adımları gerçekleştirin:

1. Bir varsayılan docker ana bilgisayar örneği oluşturun.

    ```PowerShell
    docker-machine create --driver virtualbox default
    ```
2. Varsayılan örnek yapılandırılmış ve çalışıyor olduğunu doğrulayın. (Çalışan'default ' adlı bir örnek görmeniz gerekir.

    ```PowerShell
    docker-machine ls
    ```

    ![docker-machine ls çıkış](media/vs-azure-tools-docker-setup/docker-machine-ls.png)
3. Varsayılan geçerli konak ve kabuğunuz yapılandırma.

    ```PowerShell
    docker-machine env default | Invoke-Expression
    ```
4. Etkin Docker kapsayıcılarını görüntüler. Liste boş olmalıdır.

    ```PowerShell
    docker ps
    ```

    ![docker ps çıkış](media/vs-azure-tools-docker-setup/docker-ps.png)

> [!NOTE]
> Geliştirme makinenizi yeniden başlatmanız her zaman, yerel bir docker konağı yeniden başlatmanız gerekir.
> Bunu yapmak için bir komut isteminde aşağıdaki komutu yürütün.: `docker-machine start default`.