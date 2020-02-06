---
title: Planear la aplicación de anuncios en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Planificación de la aplicación de anuncios en Skype empresarial Server Enterprise Voice, que configura qué hacer con las llamadas telefónicas a números de teléfono sin asignar de las organizaciones. Incluye requisitos para los archivos de audio.
ms.openlocfilehash: d160878030fad30dd3e91b78f54ffcdab722299f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803270"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planear la aplicación de anuncios en Skype empresarial

Planificación de la aplicación de anuncios en Skype empresarial Server Enterprise Voice, que configura qué hacer con las llamadas telefónicas a números de teléfono sin asignar de las organizaciones. Incluye requisitos para los archivos de audio.

La aplicación de anuncios de Skype empresarial Server le permite configurar el control de las llamadas telefónicas entrantes cuando el número marcado es válido para su organización, pero no está asignado a un usuario o a un teléfono. Puedes transferir estas llamadas a un destino predeterminado (a un número de teléfono, a un URI de SIP o a un correo de voz) o reproducir un anuncio de audio, o ambas opciones. La aplicación Anuncio te ayuda a evitar situaciones en las que el autor de la llamada marca un número equivocado y oye el tono de línea ocupada o el cliente SIP recibe un mensaje de error. Esta sección incluye información de planificación específica de la aplicación de anuncios.

Al implementar la aplicación de anuncios, debe configurar una tabla de números sin asignar que determine la acción que se realizará cuando alguien Marque un número sin asignar. La tabla de números sin asignar contiene rangos de números de teléfono que son válidos para la organización y especifica qué aplicación de la presentación controla cada rango. Cuando el autor de la llamada marca un número de teléfono que es válido para su organización pero que no está asignado a nadie, Skype empresarial Server busca el número en la tabla de enrutamiento de números sin asignar, identifica el intervalo en el que cae el número y enruta la llamada al Aplicación de anuncios especificada para ese intervalo. La aplicación de anuncio responde a la llamada y reproduce un mensaje de audio (si lo ha configurado para ello) y, a continuación, desconecta la llamada o la transfiere a un destino predeterminado, como a un operador. Puede usar los cmdlets del shell de administración de Skype empresarial Server para configurar varios mensajes de audio o para transferir destinos.

La forma en que configures la tabla de números no asignados depende de cómo deseas usarla. Si dispones de números específicos que ya no están en uso y deseas reproducir mensajes personalizados para cada uno de los números, puedes introducir esos números específicos en la tabla de números no asignados. Por ejemplo, si ha cambiado el número del departamento de servicio de asistencia al cliente, puedes introducir el número antiguo del servicio de asistencia al cliente y asignarlo a un anuncio que comunique el número nuevo. Si deseas reproducir un mensaje general para todas las personas que llamen a un número no asignado como, por ejemplo, a empleados que ya no pertenecen a la organización, puedes introducir intervalos para todas las extensiones válidas de la organización. Se invoca a la tabla de números no asignados siempre que el autor de la llamada marque un número que no esté asignado actualmente.

## <a name="deployment-and-requirements"></a>Requisitos e implementación

La aplicación del anuncio se instala automáticamente con la aplicación de grupo de respuesta. Las aplicaciones de grupos de presentación y respuesta son componentes estándar de una implementación de telefonía IP empresarial: cuando se implementa la telefonía IP empresarial, estas dos aplicaciones se implementan automáticamente.

### <a name="software-requirements"></a>Requisitos de software

Todos los servidores front-end o los servidores Standard Edition que ejecuten la aplicación de anuncio deben tener instalado el Windows Media Format Runtime para servidores que ejecuten Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecuten Windows Server 2012 o Windows Server 2012 R2. En Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows. Se necesita Windows Media Format Runtime o Microsoft Media Foundation para los archivos de audio de Windows Media (. WMA) que la aplicación del anuncio reproduce para los anuncios y la música.

### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de anuncios usa el **puerto 5071** para solicitudes de escucha de SIP.

> [!NOTE]
> Este puerto es el predeterminado, pero puedes cambiarlo utilizando el cmdlet **Set-CsApplicationServer**. Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Skype empresarial Server.

### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación de anuncios admite el formato de archivo de onda (. wav) y el formato de archivo de audio de Windows Media (. WMA) para música y anuncios. Los requisitos de los archivos de audio para la aplicación de anuncios son los mismos que los de la aplicación de grupo de respuesta. Si desea información detallada, mire [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).


