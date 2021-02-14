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
description: Planificación de la aplicación de anuncio en Skype Empresarial Server Telefonía IP empresarial, que configura qué hacer con las llamadas telefónicas a números de teléfono sin signo en sus organizaciones. Incluye requisitos de archivos de audio.
ms.openlocfilehash: b1929fa14b105fd8eccd0f178ae7ef77c1bdf086
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813760"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planear la aplicación Anuncio en Skype Empresarial

Planificación de la aplicación de anuncio en Skype Empresarial Server Telefonía IP empresarial, que configura qué hacer con las llamadas telefónicas a números de teléfono sin signo en sus organizaciones. Incluye requisitos de archivos de audio.

La aplicación Anuncio de Skype Empresarial Server le permite configurar el control de las llamadas telefónicas entrantes cuando el número marcado es válido para su organización, pero no está asignado a un usuario o un teléfono. Puede transferir estas llamadas a un destino predeterminado (número de teléfono, URI de SIP o correo de voz) o reproducir un anuncio de audio, o ambas opciones. La aplicación Anuncio contribuye a evitar situaciones en las que el autor de la llamada marca un número equivocado y oye el tono de línea ocupada o el cliente SIP recibe un mensaje de error. En esta sección se incluye información de planeación específica de la aplicación Anuncio.

Al implementar la aplicación Anuncio, debe configurar una tabla de números sin signo que determine la acción que se debe realizar cuando alguien marque un número sin signo. La tabla de números sin signo contiene intervalos de números de teléfono válidos para la organización y especifica qué aplicación de anuncio controla cada intervalo. Cuando un autor de la llamada marca un número de teléfono válido para su organización pero que no está asignado a nadie, Skype Empresarial Server busca el número en la tabla de enrutamiento de números sin asignar, identifica en qué intervalo se encuentra el número y enruta la llamada a la aplicación anuncio especificada para ese intervalo. La aplicación Anuncio responde a la llamada y reproduce un mensaje de audio (si lo configuró para hacerlo) y, a continuación, desconecta la llamada o la transfiere a un destino predeterminado, como a un operador. Puede usar los cmdlets del Shell de administración de Skype Empresarial Server para configurar varios mensajes de audio o transferir destinos.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Si dispone de números específicos que ya no están en uso y desea reproducir mensajes personalizados para cada uno de los números, puede introducir esos números específicos en la tabla de números no asignados. Por ejemplo, si ha cambiado el número del departamento de soporte interno, puede introducir el número antiguo de este departamento y asignarlo a un anuncio que comunique el número nuevo. Si desea reproducir un mensaje general para todas las personas que llamen a un número no asignado como, por ejemplo, a empleados que ya no pertenecen a la organización, puede introducir intervalos para todas las extensiones válidas de la organización. Se invoca a la tabla de números no asignados siempre que el autor de la llamada marque un número que no esté asignado actualmente.

## <a name="deployment-and-requirements"></a>Implementación y requisitos

La aplicación Anuncio se instala automáticamente con la aplicación Grupo de respuesta. Las aplicaciones anuncio y grupo de respuesta son componentes estándar de una implementación Telefonía IP empresarial: al implementar Telefonía IP empresarial, ambas aplicaciones se implementan automáticamente.

### <a name="software-requirements"></a>Requisitos de software

Todos los servidores front-end o servidores Standard Edition que ejecuten la aplicación Anuncio deben tener instalado El tiempo de ejecución de Windows Media Format para los servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows. El tiempo de ejecución de Windows Media Format o Microsoft Media Foundation son necesarios para los archivos de Audio de Windows Media (.wma) que reproduce la aplicación Anuncio para anuncios y música.

### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación Anuncio usa **el puerto 5071 para** las solicitudes de escucha SIP.

> [!NOTE]
> Este puertos es el predeterminado, pero puede cambiarlo utilizando el cmdlet **Set-CsApplicationServer**. Para obtener más información sobre este cmdlet, consulte la documentación del Shell de administración de Skype Empresarial Server.

### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación Anuncio admite formato de archivo Wave (.wav) y formato de archivo de audio de Windows Media (.wma) para música y anuncios. Los requisitos de archivo de audio para la aplicación Anuncio son los mismos que para la aplicación Grupo de respuesta. Si desea más información, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).


