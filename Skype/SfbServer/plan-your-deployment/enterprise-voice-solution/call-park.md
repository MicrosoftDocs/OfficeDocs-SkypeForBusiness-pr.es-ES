---
title: Plan para el parque de llamadas en Skype empresarial
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planificación del parque de llamadas en Skype empresarial Server Enterprise Voice, que permite poner llamadas en espera y transferir llamadas a departamentos. Incluye el planeamiento de capacidad, llamadas admitidas y clientes admitidos.
ms.openlocfilehash: 3effeab4afef60fb7a5021206d9fc3cd0227ceb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803200"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Plan para el parque de llamadas en Skype empresarial
 
Planificación del parque de llamadas en Skype empresarial Server Enterprise Voice, que permite poner llamadas en espera y transferir llamadas a departamentos. Incluye el planeamiento de capacidad, llamadas admitidas y clientes admitidos.
  
La aplicación de estacionamiento de llamadas permite a los usuarios de telefonía empresarial hacer lo siguiente:
  
- Poner una llamada en espera y recuperar la llamada desde el mismo teléfono o desde otro.
    
- Poner una llamada en espera para transferirla a un departamento o área general, por ejemplo, a un departamento de ventas o a un almacén donde hay un teléfono de área común.
    
- Poner una llamada en espera y conservar el teléfono original que ha respondido disponible para recibir otras llamadas.
    
Cuando un usuario detiene una llamada, Skype empresarial Server transfiere la llamada a un número temporal, denominado órbita, en el que se mantiene la llamada hasta que se recupera o se agota el tiempo de espera. Skype empresarial Server envía la órbita al usuario que ha detenido la llamada. Para recuperar la llamada estacionada, el usuario puede marcar el número de órbita o hacer clic en el botón o vínculo de órbita de la ventana Conversación. 
  
El usuario que estacionó una llamada puede notificar a alguien que recupere la llamada usando un mecanismo externo, como la mensajería instantánea (MI) o un sistema de localización, para comunicar el número de órbita a otro usuario. El usuario que estacionó la llamada puede dejar la ventana Conversación abierta para recibir una notificación cuando se recupere la llamada.
  
Dado que los intervalos de órbita son únicos globalmente, es posible recuperar las llamadas desde cualquier sitio de Skype empresarial Server o PBX si el enrutamiento está configurado correctamente. Si nadie recupera la llamada en un período de tiempo configurable, la llamada volverá a sonar para la persona que la estacionó. Si dicha persona no responde esta vez, la llamada se transferirá a un destino de conmutación por error, como un operador, si se ha configurado así. Puedes configurar el número de veces que deseas que suene la llamada antes de ser transferida de una a diez veces. Si nadie responde a una llamada transferida, la llamada se desconectará. La órbita se libera cuando se recupera la llamada o se desconecta.
  
Al implementar el estacionamiento de llamadas, necesitarás reservar intervalos de números de extensión para estacionar llamadas. Estas extensiones necesitan ser extensiones virtuales: extensiones que no tienen ningún usuario o teléfono asignado. Luego, necesitarás configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión y especificar qué servicio de aplicaciones hospeda la aplicación Estacionamiento de llamadas que administra cada intervalo. Cada grupo de servidores front-end tiene una tabla de estacionamiento de llamadas en el servidor back end correspondiente que se usa para administrar las llamadas que se aparcarán en el grupo. La lista de intervalos de órbita se almacena en el almacén de administración central y se usa para enrutar órbitas hasta el grupo de destino. Cada grupo de servidores de Skype empresarial en el que se implementa y configura la aplicación de estacionamiento de llamadas puede tener uno o más intervalos orbitales. Los intervalos de órbita deben ser únicos globalmente en toda la implementación de Skype empresarial Server. 
  
También configuras otras opciones de estacionamiento de llamadas, como, por ejemplo, el lugar al que se redirigirán las llamadas si transcurre el tiempo de espera y si la persona que está al teléfono oirá música mientras la llamada está estacionada. Asimismo, puedes especificar el archivo de música que deseas que se reproduzca mientras la llamada está en espera.
  
> [!NOTE]
> No se realiza una copia de seguridad de los archivos de música hospedada personalizada para el servicio de recuperación de desastres de Skype empresarial y se perderán si los archivos cargados en el grupo están dañados, dañados o borrados. Guarda siempre una copia de seguridad independiente de los archivos de música en espera personalizados que haya cargado para el estacionamiento de llamadas. 
  
La aplicación Estacionamiento de llamadas es un componente de la telefonía IP empresarial. Al implementar la telefonía IP empresarial, la aplicación de estacionamiento de llamadas se instala y activa automáticamente. Sin embargo, antes de poder usar el parque de llamadas, el administrador de telefonía IP debe configurarlo y habilitarlo para los usuarios mediante la Directiva de voz.
  
## <a name="deployment-and-requirements"></a>Requisitos e implementación

La aplicación de estacionamiento de llamadas se instala automáticamente al implementar la telefonía IP empresarial. Para habilitar el parque de llamadas, configure la Directiva de voz.
  
### <a name="software-requirements"></a>Requisitos de software

Todos los servidores front-end y los servidores Standard Edition en los que se implemente el parque de llamadas deben tener instalado el Windows Media Format Runtime para servidores que ejecuten Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecuten Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows. Se necesita Windows Media Format Runtime o Microsoft Media Foundation para los archivos de audio de Windows Media (. WMA) que llaman a reproducciones de estacionamiento para música en espera.
  
### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de estacionamiento de llamadas usa el **puerto 5075** para solicitudes de escucha de SIP.
    
> [!NOTE]
> Este puerto es una configuración predeterminada que puedes cambiar con el cmdlet **Set-CsApplicationServer**. Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.
  
### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

La aplicación de estacionamiento de llamadas solo admite archivos de audio de Windows Media (. WMA) para música en espera. Puedes usar Microsoft Expression Encoder 4 para personalizar los archivos para la música en espera. Para descargar Expression Encoder 4, consulta ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Usa la herramienta para convertir el archivo en un formato .wma. El formato recomendado para los archivos de reactivar música en espera de llamadas es media audio 9, 44 kHz, 16 bits, mono, CBR, 32 kbps.
  
> [!NOTE]
> El archivo convertido se reproduce por el teléfono solo a 16 kHz, aunque se grabó a 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Llamadas y clientes compatibles

Los siguientes clientes y tipos de llamadas son compatibles con el parque de llamadas
  
### <a name="clients-supported-for-parking-calls"></a>Clientes compatibles con el estacionamiento de llamadas

Se pueden estacionar las llamadas de cualquier IP, central de conmutación (PBX), red telefónica conmutada (RTC) o teléfono móvil.
  
> [!NOTE]
> Únicamente se pueden estacionar las llamadas de audio. No se pueden estacionar los mensajes instantáneos ni las conferencias. 
  
Los siguientes clientes pueden usar el activador de llamadas para detener llamadas:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Operador de Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Los teléfonos móviles no pueden usar el parque de llamadas para detener llamadas. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clientes compatibles con la recuperación de llamadas

Los intervalos de órbitas están configurados como bloques de extensiones virtuales (extensiones sin ningún usuario ni teléfono asignado). Cuando configuras órbitas como extensiones virtuales, teléfonos móviles y teléfono RTC, no puedes recuperar llamadas estacionadas.
  
Los usuarios federados no pueden recuperar llamadas estacionadas.
  
Los siguientes clientes pueden recuperar llamadas estacionadas en el parque de llamadas:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Operador de Lync 2010
    
- Lync Phone Edition
    
- Teléfonos IP de área común
    
- Teléfonos no basados en IP que están conectados a la infraestructura de Skype empresarial Server, incluidos teléfonos de área común y teléfonos de central de conmutación (PBX)
    
## <a name="call-park-capacity-planning"></a>Planificación de la capacidad del estacionamiento de llamadas

En la siguiente tabla se describe el modelo de usuario de estacionamiento de llamadas que puede usar como base para los requisitos de planes de capacidad.
  
> [!IMPORTANT]
> Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debería poder administrar las cargas de trabajo de los servicios de estacionamiento de llamadas en ambos grupos. 
  
**Modelo de usuario de estacionamiento de llamadas**

|**Métrica**|**Por grupo <br/> front-end (con 8 servidores frontales)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Tasa de estacionamiento  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Tasa de recuperación de llamadas estacionadas  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Promedio de duración del estacionamiento  <br/> |60 segundos  <br/> |60 segundos  <br/> |
   

