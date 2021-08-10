---
title: Planear la aplicación Anuncio en Skype Empresarial
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
description: Planeación de la aplicación de anuncio en Skype Empresarial Server Telefonía IP empresarial, que configura qué hacer con las llamadas telefónicas a números de teléfono sinsignación en las organizaciones. Incluye requisitos de archivo de audio.
ms.openlocfilehash: caec21da11ce4fe44738b57872acc5c1b0533b2536b90304ea83332deae1aeaf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306971"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planear la aplicación Anuncio en Skype Empresarial

Planeación de la aplicación de anuncio en Skype Empresarial Server Telefonía IP empresarial, que configura qué hacer con las llamadas telefónicas a números de teléfono sinsignación en las organizaciones. Incluye requisitos de archivo de audio.

La aplicación de Skype Empresarial Server anuncio le permite configurar el control de llamadas entrantes cuando el número marcado es válido para su organización, pero no está asignado a un usuario o un teléfono. Puede transferir estas llamadas a un destino predeterminado (número de teléfono, URI de SIP o correo de voz) o reproducir un anuncio de audio, o ambas opciones. La aplicación Anuncio contribuye a evitar situaciones en las que el autor de la llamada marca un número equivocado y oye el tono de línea ocupada o el cliente SIP recibe un mensaje de error. En esta sección se incluye información de planeación específica de la aplicación Anuncio

Al implementar la aplicación Anuncio, debe configurar una tabla de números sinsignación que determine la acción que se debe realizar cuando alguien marca un número sinsignación. La tabla de números sinsignación contiene intervalos de números de teléfono que son válidos para la organización y especifica qué aplicación de anuncio controla cada intervalo. Cuando un autor de la llamada marca un número de teléfono válido para su organización pero no está asignado a nadie, Skype Empresarial Server busca el número en la tabla de enrutamiento de números sin asignar, identifica el intervalo en el que se encuentra el número y enruta la llamada a la aplicación de anuncio especificada para ese intervalo. La aplicación Anuncio responde a la llamada y reproduce un mensaje de audio (si la configuró para hacerlo) y, a continuación, desconecta la llamada o la transfiere a un destino predeterminado, como a un operador. Puede usar los cmdlets Skype Empresarial Server Shell de administración para configurar varios mensajes de audio o transferir destinos.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Si dispone de números específicos que ya no están en uso y desea reproducir mensajes personalizados para cada uno de los números, puede introducir esos números específicos en la tabla de números no asignados. Por ejemplo, si ha cambiado el número del departamento de soporte interno, puede introducir el número antiguo de este departamento y asignarlo a un anuncio que comunique el número nuevo. Si desea reproducir un mensaje general para todas las personas que llamen a un número no asignado como, por ejemplo, a empleados que ya no pertenecen a la organización, puede introducir intervalos para todas las extensiones válidas de la organización. Se invoca a la tabla de números no asignados siempre que el autor de la llamada marque un número que no esté asignado actualmente.

## <a name="deployment-and-requirements"></a>Implementación y requisitos

La aplicación Anuncio se instala automáticamente con la aplicación Grupo de respuesta. Las aplicaciones Announcement y Response Group son componentes estándar de una implementación Telefonía IP empresarial: al implementar Telefonía IP empresarial, ambas aplicaciones se implementan automáticamente.

### <a name="software-requirements"></a>Requisitos de software

Todos los servidores front-end o servidores Standard Edition que ejecuten la aplicación Anuncio deben tener el tiempo de ejecución de formato multimedia de Windows instalado para servidores que ejecuten Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecuten Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de Windows Desktop Experience. Windows Media Format Runtime o Microsoft Media Foundation es necesario para los archivos Windows Media Audio (.wma) que reproduce la aplicación Anuncio para anuncios y música.

### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación Anuncio usa **el puerto 5071 para** las solicitudes de escucha SIP.

> [!NOTE]
> Este puertos es el predeterminado, pero puede cambiarlo utilizando el cmdlet **Set-CsApplicationServer**. Para obtener más información acerca de este cmdlet, consulte la Skype Empresarial Server del Shell de administración.

### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación Announcement es compatible con el formato de archivo Wave (.wav) y Windows formato de archivo de audio multimedia (.wma) para música y anuncios. Los requisitos de archivos de audio para la aplicación Anuncio son los mismos que para la aplicación grupo de respuesta. Si desea más información, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).