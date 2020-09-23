---
title: Agregar almacén de archivos de director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: Debe especificar un recurso compartido de archivos para usarlo como almacén de archivos de los directores. Puede utilizar un recurso compartido de archivos existente como almacén o elegir uno nuevo especificando el nombre de dominio completo (FQDN) del servidor de archivos en el que se deba ubicar el recurso compartido de archivos y un nombre de carpeta para el nuevo recurso compartido de archivos.
ms.openlocfilehash: 4c68e592568f160575433d5b4f772eadf8c81a2e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215541"
---
# <a name="add-director-file-store"></a>Agregar almacén de archivos de director

Debe especificar un recurso compartido de archivos para usarlo como almacén de archivos de los directores. Puede utilizar un recurso compartido de archivos existente como almacén o elegir uno nuevo especificando el nombre de dominio completo (FQDN) del servidor de archivos en el que se deba ubicar el recurso compartido de archivos y un nombre de carpeta para el nuevo recurso compartido de archivos.

> [!IMPORTANT]
> Al agregar directores a una topología, la publicación de topología requiere un acceso adecuado para configurar el almacén de archivos y las listas de control de acceso discrecional (DACL) en el recurso compartido de archivos que se utilizará para el almacén de archivos. Para ello, es necesario que al ejecutar el Topology Builder y publicar la nueva topología, haya iniciado una sesión con una cuenta con todos los permisos de control (lectura/escritura/modificación) para el recurso compartido de archivos.

Para obtener más información sobre la compatibilidad de almacenamiento de los recursos compartidos de archivos, consulte [File Storage support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) en la documentación de compatibilidad y [SQL Server Data and log file Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación sobre implementación. Para más información sobre la combinación del recurso compartido de archivos, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación sobre compatibilidad. Para más información sobre cómo diseñar la topología para directores, consulte [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) en la documentación sobre implementación.


