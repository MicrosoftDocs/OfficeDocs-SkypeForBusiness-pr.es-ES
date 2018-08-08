---
title: Plan para el estacionamiento de llamadas en Skype para la empresa
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planeación de estacionamiento de llamadas en Skype para Business Server Enterprise Voice, que permite que las llamadas de puesta en espera y la transferencia de llamadas a departamentos. Incluye el planeamiento de capacidad, llamadas admitidas y clientes admitidos.
ms.openlocfilehash: a675100f8b40e1ab293c0240ea0acbe3beb7fa27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988553"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Plan para el estacionamiento de llamadas en Skype para la empresa
 
Planeación de estacionamiento de llamadas en Skype para Business Server Enterprise Voice, que permite que las llamadas de puesta en espera y la transferencia de llamadas a departamentos. Incluye el planeamiento de capacidad, llamadas admitidas y clientes admitidos.
  
La aplicación de estacionamiento de llamadas permite a los usuarios de Enterprise Voice hacer lo siguiente:
  
- Poner una llamada en espera y recuperar la llamada desde el mismo teléfono o desde otro.
    
- Poner una llamada en espera para transferirla a un departamento o área general, por ejemplo, a un departamento de ventas o a un almacén donde hay un teléfono de área común.
    
- Poner una llamada en espera y conservar el teléfono original que ha respondido disponible para recibir otras llamadas.
    
Cuando un parques de usuario, una llamada de Skype para Business Server transfiere la llamada a un número temporal, denominado una órbita, donde se mantiene la llamada hasta que se recupera o se agota el tiempo. Skype para Business Server envía la órbita al usuario que estacionar la llamada. Para recuperar la llamada estacionada, el usuario puede marcar el número de órbita o hacer clic en el botón o vínculo de órbita de la ventana Conversación. 
  
El usuario que estacionó una llamada puede notificar a alguien que recupere la llamada usando un mecanismo externo, como la mensajería instantánea (MI) o un sistema de localización, para comunicar el número de órbita a otro usuario. El usuario que estacionó la llamada puede dejar la ventana Conversación abierta para recibir una notificación cuando se recupere la llamada.
  
Debido a que los intervalos de Órbitas son globalmente únicos, es posible recuperar las llamadas de cualquier Skype para sitio de Business Server o teléfono PBX si el enrutamiento está configurado correctamente. Si nadie recupera la llamada en un período de tiempo configurable, la llamada volverá a sonar para la persona que la estacionó. Si dicha persona no responde esta vez, la llamada se transferirá a un destino de conmutación por error, como un operador, si se ha configurado así. Puedes configurar el número de veces que deseas que suene la llamada antes de ser transferida de una a diez veces. Si nadie responde a una llamada transferida, la llamada se desconectará. La órbita se libera cuando se recupera la llamada o se desconecta.
  
Al implementar el estacionamiento de llamadas, necesitarás reservar intervalos de números de extensión para estacionar llamadas. Estas extensiones necesitan ser extensiones virtuales: extensiones que no tienen ningún usuario o teléfono asignado. Luego, necesitarás configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión y especificar qué servicio de aplicaciones hospeda la aplicación Estacionamiento de llamadas que administra cada intervalo. Cada grupo de servidores Front-End tiene una tabla de estacionamiento de llamadas en el correspondiente servidor Back-End que se usa para administrar las llamadas que están estacionadas en el grupo de servidores. La lista de intervalos de Órbitas se almacena en la Administración Central almacenar y se usa para enrutar Órbitas al grupo de servidores de destino. Cada Skype para profesionales de servidores donde se ha implementado y configurada la aplicación de estacionamiento de llamadas puede tener uno o varios intervalos de Órbitas. Intervalos de Órbitas deben ser únicos globalmente a través de la Skype para la implementación de Business Server. 
  
También configuras otras opciones de estacionamiento de llamadas, como, por ejemplo, el lugar al que se redirigirán las llamadas si transcurre el tiempo de espera y si la persona que está al teléfono oirá música mientras la llamada está estacionada. Asimismo, puedes especificar el archivo de música que deseas que se reproduzca mientras la llamada está en espera.
  
> [!NOTE]
> Archivos de música en espera personalizados para el estacionamiento de llamadas no se copia como parte de la Skype para el proceso de recuperación ante desastres de Business Server y se perderán si están dañados, dañados o borrar los archivos cargados en el grupo de servidores. Guarda siempre una copia de seguridad independiente de los archivos de música en espera personalizados que haya cargado para el estacionamiento de llamadas. 
  
La aplicación Estacionamiento de llamadas es un componente de la telefonía IP empresarial. Al implementar Enterprise Voice, la aplicación de estacionamiento de llamadas está instalada y se activan automáticamente. Sin embargo, antes de poder usar estacionamiento de llamadas, el Administrador de Enterprise Voice debe configurarlo y habilitarlo para los usuarios a través de la directiva de voz.
  
## <a name="deployment-and-requirements"></a>Requisitos e implementación

La aplicación de estacionamiento de llamadas se instala automáticamente al implementar Enterprise Voice. Habilitar estacionamiento de llamadas mediante la configuración de directiva de voz.
  
### <a name="software-requirements"></a>Requisitos de software

Todos los servidores Front-End y Standard Edition de los servidores donde se implementa el estacionamiento de llamadas deben tener instalado para los servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 o Windows Server Windows Media Format Runtime 2012 R2. Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows. Se requiere para Windows Media Audio (.wma) los archivos que se reproduce el estacionamiento de llamadas para la música en espera el tiempo de ejecución de Windows Media Format o Microsoft Media Foundation.
  
### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de estacionamiento de llamadas usa **5075 de puerto** para solicitudes de escucha SIP.
    
> [!NOTE]
> Este puerto es una configuración predeterminada que se puede cambiar mediante el cmdlet **Set-CsApplicationServer** . Para obtener más información acerca de este cmdlet, vea la documentación del Shell de administración de Lync Server.
  
### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

El estacionamiento de llamadas aplicación admite sólo los archivos de Windows Media Audio (.wma) para la música en espera. Puedes usar Microsoft Expression Encoder 4 para personalizar los archivos para la música en espera. Para descargar expresión codificador 4, vea ["Expresión codificador 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Usa la herramienta para convertir el archivo en un formato .wma. El formato recomendado para los archivos de música en espera de estacionamiento de llamadas es Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.
  
> [!NOTE]
> El archivo convertido se reproduce por el teléfono solo a 16 kHz, aunque se grabó a 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Llamadas y clientes compatibles

Se admiten los siguientes clientes y tipos de llamadas para el estacionamiento de llamadas
  
### <a name="clients-supported-for-parking-calls"></a>Clientes compatibles con el estacionamiento de llamadas

Se pueden estacionar las llamadas de cualquier IP, central de conmutación (PBX), red telefónica conmutada (RTC) o teléfono móvil.
  
> [!NOTE]
> Únicamente se pueden estacionar las llamadas de audio. No se pueden estacionar los mensajes instantáneos ni las conferencias. 
  
Los siguientes clientes pueden usar estacionamiento de llamadas para estacionar llamadas:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Operador de Skype Empresarial
    
- Lync Phone Edition
    
> [!NOTE]
> Teléfonos móviles no puede usar el estacionamiento de llamadas para estacionar llamadas. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clientes compatibles con la recuperación de llamadas

Los intervalos de órbitas están configurados como bloques de extensiones virtuales (extensiones sin ningún usuario ni teléfono asignado). Cuando configuras órbitas como extensiones virtuales, teléfonos móviles y teléfono RTC, no puedes recuperar llamadas estacionadas.
  
Los usuarios federados no pueden recuperar llamadas estacionadas.
  
Los siguientes clientes pueden recuperar llamadas que están estacionadas en el estacionamiento de llamadas:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Operador de Skype Empresarial
    
- Lync Phone Edition
    
- Teléfonos IP de área común
    
- Los teléfonos no IP que están conectados a la Skype para la infraestructura de Business Server, incluidos los teléfonos de área común y teléfonos de central de conmutación (PBX) de exchange
    
## <a name="call-park-capacity-planning"></a>Planificación de la capacidad del estacionamiento de llamadas

En la siguiente tabla se describe el modelo de usuario de estacionamiento de llamadas que puede usar como base para los requisitos de planeación de capacidad.
  
> [!IMPORTANT]
> Tenga en cuenta que, para la planeación de capacidad del recuperación de desastres, cada grupo de servidores de un grupo formado en par debe ser capaz de controlar las cargas de trabajo para los servicios de estacionamiento de llamadas en ambos grupos. 
  
**Modelo de usuario de estacionamiento de llamadas**

|**Métrica**|**Por grupo de servidores Front-End <br/> (con 8 servidores Front-End)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Tasa de estacionamiento  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Tasa de recuperación de llamadas estacionadas  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Promedio de duración del estacionamiento  <br/> |60 segundos  <br/> |60 segundos  <br/> |
   

