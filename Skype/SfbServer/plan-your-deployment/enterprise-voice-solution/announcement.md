---
title: Planeación de la aplicación de anuncio en Skype para la empresa
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planeación de la aplicación de anuncio en Skype para Business Server Enterprise Voice, que configura qué hacer con las llamadas telefónicas a los números de teléfono sin asignar en sus organizaciones. Incluye requisitos para los archivos de audio.
ms.openlocfilehash: 2642dc13653f18520371b31c9e5ff41bc6a479d3
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882108"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Planeación de la aplicación de anuncio en Skype para la empresa

Planeación de la aplicación de anuncio en Skype para Business Server Enterprise Voice, que configura qué hacer con las llamadas telefónicas a los números de teléfono sin asignar en sus organizaciones. Incluye requisitos para los archivos de audio.

El Skype para aplicación de anuncio de servidor empresarial le permite configurar el control de las llamadas telefónicas recibidas cuando el número marcado es válido para la organización, pero no se asigna a un usuario o un teléfono. Puedes transferir estas llamadas a un destino predeterminado (a un número de teléfono, a un URI de SIP o a un correo de voz) o reproducir un anuncio de audio, o ambas opciones. La aplicación Anuncio te ayuda a evitar situaciones en las que el autor de la llamada marca un número equivocado y oye el tono de línea ocupada o el cliente SIP recibe un mensaje de error. En esta sección se incluye información de diseño que es específica de la aplicación de anuncio

Cuando se implementa la aplicación de anuncio, debe configurar una tabla de números sin asignar que determina la acción que se realizará cuando alguien llame a un número sin asignar. La tabla de números no asignada contiene intervalos de números de teléfono que son válidos para la organización y especifica qué aplicación de anuncio administra cada intervalo. Llaman a un número de teléfono que es válido para la organización, pero no se asigna a todas las personas, Skype para Business Server busca el número en la tabla de enrutamiento de números sin asignar, identifica qué intervalo entra en el número y enruta la llamada a la Aplicación de anuncio especificada de ese rango. La aplicación de anuncio responde a la llamada y reproduce un mensaje de audio (si se ha configurado para ello) y, a continuación, desconecta la llamada o transfiere a un destino predeterminado, por ejemplo, a un operador. Puede usar Skype para los cmdlets del Shell de administración de servidor empresarial para configurar varios mensajes de audioconferencias o transferir los destinos.

La forma en que configures la tabla de números no asignados depende de cómo deseas usarla. Si dispones de números específicos que ya no están en uso y deseas reproducir mensajes personalizados para cada uno de los números, puedes introducir esos números específicos en la tabla de números no asignados. Por ejemplo, si ha cambiado el número del departamento de servicio de asistencia al cliente, puedes introducir el número antiguo del servicio de asistencia al cliente y asignarlo a un anuncio que comunique el número nuevo. Si deseas reproducir un mensaje general para todas las personas que llamen a un número no asignado como, por ejemplo, a empleados que ya no pertenecen a la organización, puedes introducir intervalos para todas las extensiones válidas de la organización. Se invoca a la tabla de números no asignados siempre que el autor de la llamada marque un número que no esté asignado actualmente.

## <a name="deployment-and-requirements"></a>Requisitos e implementación

Aplicación del anuncio se instala automáticamente con la aplicación de grupo de respuesta. Las aplicaciones de anuncio y grupo de respuesta son componentes estándares de una implementación de Enterprise Voice: al implementar Enterprise Voice, ambos de estas aplicaciones se implementan automáticamente.

### <a name="software-requirements"></a>Requisitos de software

Todos los servidores Front-End o servidores Standard Edition que ejecutan la aplicación de anuncio deben tener instalado para los servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 Windows Media Format Runtime o Windows Server 2012 R2. Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows. El tiempo de ejecución de Windows Media Format o Microsoft Media Foundation es necesario para los archivos de Windows Media Audio (.wma) que se reproduce la aplicación de anuncio para música y anuncios.

### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de anuncio usa **5071 de puerto** para solicitudes de escucha SIP.

> [!NOTE]
> Este puerto es el valor predeterminado, que se puede cambiar mediante el cmdlet **Set-CsApplicationServer** . Para obtener más información acerca de este cmdlet, vea el Skype para la documentación del Shell de administración de servidor empresarial.

### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación de anuncio es compatible con formato de archivo de onda (.wav) y audio de Windows Media (.wma) formato de archivo de música y anuncios. Requisitos de archivo de audio para la aplicación de anuncio son los mismos que para la aplicación de grupo de respuesta. Para obtener información detallada, vea [Requisitos técnicos para grupos de respuesta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).


