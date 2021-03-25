---
title: Plan for the Announcement application in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planeación de la aplicación de anuncio en Skype Empresarial Server Telefonía IP empresarial, que configura qué hacer con las llamadas telefónicas a números de teléfono sinsignados en sus organizaciones. Incluye requisitos de archivo de audio.
ms.openlocfilehash: e1309fe58942f3b9cd720b3643966ae9494bb0cb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112716"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Plan for the Announcement application in Skype for Business

Planeación de la aplicación de anuncio en Skype Empresarial Server Telefonía IP empresarial, que configura qué hacer con las llamadas telefónicas a números de teléfono sinsignados en sus organizaciones. Incluye requisitos de archivo de audio.

La aplicación de anuncio de Skype Empresarial Server permite configurar el control de las llamadas telefónicas entrantes cuando el número marcado es válido para su organización, pero no está asignado a un usuario o un teléfono. Puede transferir estas llamadas a un destino predeterminado (número de teléfono, URI de SIP o correo de voz) o reproducir un anuncio de audio, o ambas opciones. La aplicación Anuncio contribuye a evitar situaciones en las que el autor de la llamada marca un número equivocado y oye el tono de línea ocupada o el cliente SIP recibe un mensaje de error. En esta sección se incluye información de planeación específica de la aplicación Anuncio

Al implementar la aplicación Anuncio, debe configurar una tabla de números sinsignación que determine la acción que se debe realizar cuando alguien marca un número sinsignación. La tabla de números sinsignación contiene intervalos de números de teléfono que son válidos para la organización y especifica qué aplicación de anuncio controla cada intervalo. Cuando un autor de la llamada marca un número de teléfono válido para su organización pero no está asignado a nadie, Skype Empresarial Server busca el número en la tabla de enrutamiento de números sin asignar, identifica el intervalo en el que se encuentra el número y enruta la llamada a la aplicación de anuncio especificada para ese intervalo. La aplicación Anuncio responde a la llamada y reproduce un mensaje de audio (si la configuró para hacerlo) y, a continuación, desconecta la llamada o la transfiere a un destino predeterminado, como a un operador. Puede usar cmdlets del Shell de administración de Skype Empresarial Server para configurar varios mensajes de audio o transferir destinos.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Si dispone de números específicos que ya no están en uso y desea reproducir mensajes personalizados para cada uno de los números, puede introducir esos números específicos en la tabla de números no asignados. Por ejemplo, si ha cambiado el número del departamento de soporte interno, puede introducir el número antiguo de este departamento y asignarlo a un anuncio que comunique el número nuevo. Si desea reproducir un mensaje general para todas las personas que llamen a un número no asignado como, por ejemplo, a empleados que ya no pertenecen a la organización, puede introducir intervalos para todas las extensiones válidas de la organización. Se invoca a la tabla de números no asignados siempre que el autor de la llamada marque un número que no esté asignado actualmente.

## <a name="deployment-and-requirements"></a>Implementación y requisitos

La aplicación Anuncio se instala automáticamente con la aplicación Grupo de respuesta. Las aplicaciones de anuncio y grupo de respuesta son componentes estándar de una implementación Telefonía IP empresarial: al implementar Telefonía IP empresarial, ambas aplicaciones se implementan automáticamente.

### <a name="software-requirements"></a>Requisitos de software

Todos los servidores front-end o los servidores Standard Edition que ejecuten la aplicación Anuncio deben tener instalado Windows Media Format Runtime para servidores que ejecuten Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecuten Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows. Windows Media Format Runtime o Microsoft Media Foundation es necesario para los archivos de Windows Media Audio (.wma) que la aplicación Anuncio reproduce para anuncios y música.

### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación Anuncio usa **el puerto 5071 para** las solicitudes de escucha SIP.

> [!NOTE]
> Este puertos es el predeterminado, pero puede cambiarlo utilizando el cmdlet **Set-CsApplicationServer**. Para obtener más información acerca de este cmdlet, consulte la documentación del Shell de administración de Skype Empresarial Server.

### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación Announcement admite formato de archivo Wave (.wav) y formato de archivo de audio de Windows Media (.wma) para música y anuncios. Los requisitos de archivos de audio para la aplicación Anuncio son los mismos que para la aplicación grupo de respuesta. Si desea más información, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).