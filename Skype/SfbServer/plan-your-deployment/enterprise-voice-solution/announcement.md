---
title: Planificar la aplicación de anuncio en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planificación para la aplicación de anuncio en Skype para Telefonía IP empresarial de Business Server, que configura qué hacer con las llamadas de teléfono a los números no asignados en las organizaciones. Incluye requisitos para los archivos de audio.
ms.openlocfilehash: c7ed700c749f1d5692b78c931e225fee5d0497be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-the-announcement-application-in-skype-for-business-2015"></a>Planificar la aplicación de anuncio en Skype Empresarial 2015
 
Planificación para la aplicación de anuncio en Skype para Telefonía IP empresarial de Business Server, que configura qué hacer con las llamadas de teléfono a los números no asignados en las organizaciones. Incluye requisitos para los archivos de audio.
  
El Skype para aplicación de anuncio de servidor empresarial permite configurar el control de llamadas de teléfono entrantes cuando el número marcado es válido para su organización, pero no está asignado a un usuario o un teléfono. Puedes transferir estas llamadas a un destino predeterminado (a un número de teléfono, a un URI de SIP o a un correo de voz) o reproducir un anuncio de audio, o ambas opciones. La aplicación Anuncio te ayuda a evitar situaciones en las que el autor de la llamada marca un número equivocado y oye el tono de línea ocupada o el cliente SIP recibe un mensaje de error. Esta sección incluye información que es específica de la aplicación de anuncio de planificación
  
Al implementar la aplicación de anuncio, debe configurar una tabla de números sin asignar que determina la acción que se realizará cuando alguien marca un número sin asignar. La tabla de números sin asignar contiene intervalos de números de teléfono que son válidos para la organización y especifica qué aplicación de anuncio controla cada rango. Cuando un llamador marca un número de teléfono que es válido para su organización pero que no está asignado a nadie, Skype para Business Server busca el número en la tabla de enrutamiento de números sin asignar, identifica qué intervalo el número cae en y enruta la llamada a la Aplicación de anuncio especificado para ese intervalo. La aplicación de anuncio responde a la llamada y reproduce un mensaje de audio (si está configurado para ello) y la llamada desconecta o transfiere a un destino predeterminado, por ejemplo, a un operador. Puede utilizar Skype para los cmdlets del Shell de administración de servidor de Business para configurar varios mensajes de audio o transferencia de destinos.
  
La forma en que configures la tabla de números no asignados depende de cómo deseas usarla. Si dispones de números específicos que ya no están en uso y deseas reproducir mensajes personalizados para cada uno de los números, puedes introducir esos números específicos en la tabla de números no asignados. Por ejemplo, si ha cambiado el número del departamento de servicio de asistencia al cliente, puedes introducir el número antiguo del servicio de asistencia al cliente y asignarlo a un anuncio que comunique el número nuevo. Si deseas reproducir un mensaje general para todas las personas que llamen a un número no asignado como, por ejemplo, a empleados que ya no pertenecen a la organización, puedes introducir intervalos para todas las extensiones válidas de la organización. Se invoca a la tabla de números no asignados siempre que el autor de la llamada marque un número que no esté asignado actualmente.
  
## <a name="deployment-and-requirements"></a>Requisitos e implementación

Aplicación de la presentación se instala automáticamente con la aplicación de grupo de respuesta. Las aplicaciones de presentación y el grupo de respuesta son los componentes estándar de una implementación de Telefonía IP empresarial: al implementar la Telefonía IP empresarial, ambas de estas aplicaciones se implementan automáticamente. 
  
### <a name="software-requirements"></a>Requisitos de software

Servidores frontales o Standard Edition todos los servidores que ejecutan la aplicación de anuncio deben tener Windows Media Format Runtime instalado en servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecutan Windows Server 2012 o R2 de Windows Server 2012. Para Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows. Windows Media Format Runtime o Microsoft Media Foundation es necesario para los archivos de Windows Media Audio (.wma) que reproduce la aplicación de anuncio para anuncios y música. 
  
### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de anuncio utiliza **5071 de puerto** para solicitudes de escucha de SIP.
    
> [!NOTE]
> Este puerto es el predeterminado, que se puede cambiar mediante el cmdlet **Set-CsApplicationServer** . Para obtener más información acerca de este cmdlet, vea el Skype para la documentación del Shell de administración de servidor empresarial.
  
### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación de anuncio admite el formato de archivo de onda (.wav) y de audio de Windows Media (.wma) formato de archivo de música y anuncios. Requisitos de archivo de audio para la aplicación de anuncio son los mismos que para la aplicación de grupo de respuesta. Para obtener más información, consulte [Los requisitos técnicos para los grupos de respuesta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).
  

