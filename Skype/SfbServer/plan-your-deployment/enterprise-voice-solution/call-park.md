---
title: Planificar el estacionamiento de llamadas en Skype Empresarial
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planificar el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial, lo que permite poner llamadas en espera y transferir llamadas a los departamentos. Incluye la planeación de la capacidad, las llamadas admitidas y los clientes compatibles.
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825930"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planificar el estacionamiento de llamadas en Skype Empresarial
 
Planificar el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial, lo que permite poner llamadas en espera y transferir llamadas a los departamentos. Incluye la planeación de la capacidad, las llamadas admitidas y los clientes compatibles.
  
La aplicación Estacionamiento de llamadas Telefonía IP empresarial usuarios pueden hacer lo siguiente:
  
- Poner una llamada en espera y recuperar la llamada desde el mismo teléfono o desde otro.
    
- Poner una llamada en espera para transferirla a un departamento o área general, por ejemplo, a un departamento de ventas o a un almacén donde hay un teléfono de área común.
    
- Poner una llamada en espera y conservar el teléfono original que ha respondido disponible para recibir otras llamadas.
    
Cuando un usuario estaciona una llamada, Skype Empresarial Server transfiere la llamada a un número temporal, denominado órbita, donde la llamada se mantiene hasta que se recupera o se hace el tiempo de espera. Skype Empresarial Server envía la órbita al usuario que estacionó la llamada. Para recuperar la llamada estacionada, el usuario puede marcar el número de órbita o hacer clic en el botón o vínculo de órbita de la ventana Conversación. 
  
El usuario que estacionó una llamada puede notificar a alguien que recupere la llamada usando un mecanismo externo, como la mensajería instantánea (MI) o un sistema de paginación, para comunicar el número de órbita a otro usuario. El usuario que estacionó la llamada puede dejar la ventana Conversación abierta para recibir una notificación cuando se recupere la llamada.
  
Dado que los intervalos de órbitas son únicos globalmente, es posible recuperar llamadas desde cualquier sitio de Skype Empresarial Server o teléfono PBX si el enrutamiento está configurado correctamente. Si nadie recupera la llamada en un período de tiempo configurable, la llamada volverá a sonar para la persona que la estacionó. Si dicha persona no responde esta vez, la llamada se transferirá a un destino de conmutación por error, como un operador, si se ha configurado así. Puede configurar el número de veces que desea que suene la llamada antes de ser transferida de una a diez veces. Si nadie responde a una llamada transferida, la llamada se desconectará. La órbita se libera cuando se recupera la llamada o se desconecta.
  
Al implementar Estacionamiento de llamadas, deberá reservar intervalos de números de extensión (órbitas) para estacionar llamadas. Estas extensiones deben ser extensiones virtuales: extensiones que no tienen ningún usuario o teléfono asignado. A continuación, deberá configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión y especificar qué servicio de aplicaciones hospeda la aplicación Estacionamiento de llamadas que administra cada intervalo. Cada grupo de servidores front-end dispone de una tabla de estacionamiento de llamadas en el servidor back-end correspondiente que se usa para administrar las llamadas que se estacionan en el grupo de servidores. La lista de intervalos de órbitas se almacena en el almacén de administración central y se usa para enrutar órbitas al grupo de servidores de destino. Cada grupo de Skype Empresarial Server en el que se implementa y configura la aplicación estacionamiento de llamadas puede tener uno o varios intervalos de órbitas. Los intervalos de órbitas deben ser únicos globalmente en toda la implementación de Skype Empresarial Server. 
  
También configura otras opciones de Estacionamiento de llamadas, como, por ejemplo, el lugar al que se redirigirán las llamadas si transcurre el tiempo de espera y si la persona que está al teléfono oirá música mientras la llamada está estacionada. Asimismo, puede especificar el archivo de música que desea que se reproduzca mientras la llamada está en espera.
  
> [!NOTE]
> Los archivos de música en espera personalizados para el estacionamiento de llamadas no se copian como parte del proceso de recuperación ante desastres de Skype Empresarial Server y se perderán si los archivos cargados en el grupo están dañados o borrados. Guarde siempre una copia de seguridad independiente de los archivos de música en espera que haya cargado para Estacionamiento de llamadas. 
  
La aplicación Estacionamiento de llamadas es un componente de Enterprise Voice. Al implementar Enterprise Voice, la aplicación Estacionamiento de llamadas se instalará y activará de forma automática. Sin embargo, para poder usar el estacionamiento de llamadas, el administrador de Enterprise Voice deberá configurarlo y habilitarlo para los usuarios mediante una directiva de voz.
  
## <a name="deployment-and-requirements"></a>Implementación y requisitos

La aplicación Estacionamiento de llamadas se instala automáticamente al implementar Telefonía IP empresarial. Para habilitar el estacionamiento de llamadas, configure la directiva de voz.
  
### <a name="software-requirements"></a>Requisitos de software

Todos los servidores front-end y servidores Standard Edition en los que se implementa el estacionamiento de llamadas deben tener instalado El tiempo de ejecución de Windows Media Format para los servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, El tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows. El tiempo de ejecución de Windows Media Format o Microsoft Media Foundation son necesarios para los archivos de Audio de Windows Media (.wma) que el estacionamiento de llamadas reproduce para la música en espera.
  
### <a name="port-requirements"></a>Requisitos de puerto

La aplicación Estacionamiento de llamadas **usa el puerto 5075 para**  las solicitudes de escucha SIP.
    
> [!NOTE]
> Este puerto es una configuración predeterminada que puede cambiar mediante el cmdlet **Set-CsApplicationServer**. Para obtener más información acerca de este cmdlet, consulte la documentación del Shell de administración de Lync Server.
  
### <a name="audio-file-requirements"></a>Requisitos de archivo de audio

La aplicación Estacionamiento de llamadas solo admite archivos de Audio de Windows Media (.wma) para la música en espera. Puede usar Microsoft Expression Encoder 4 para personalizar los archivos para la música en espera. Para descargar Expression Encoder 4, consulte ["Expression Encoder 4".](https://go.microsoft.com/fwlink/p/?linkId=202843) Use la herramienta para convertir el archivo en un formato .wma. El formato recomendado para los archivos de música en espera de estacionamiento de llamadas es Audio multimedia a 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.
  
> [!NOTE]
> El archivo convertido se reproduce por el teléfono solo a 16 kHz, aunque se grabó a 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Llamadas y clientes admitidos

Los siguientes clientes y tipos de llamadas son compatibles con el estacionamiento de llamadas
  
### <a name="clients-supported-for-parking-calls"></a>Clientes admitidos para el estacionamiento de llamadas

Se pueden estacionar las llamadas de cualquier IP, PBX, RTC o teléfono móvil.
  
> [!NOTE]
> Únicamente se pueden estacionar las llamadas de audio. No se pueden estacionar los mensajes instantáneos ni las conferencias. 
  
Los siguientes clientes pueden usar el estacionamiento de llamadas para estacionar llamadas:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> Los teléfonos móviles no pueden usar el estacionamiento de llamadas para estacionar llamadas. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clientes admitidos para la recuperación de llamadas

Los intervalos de órbitas están configurados como bloques de extensiones virtuales (extensiones sin ningún usuario ni teléfono asignado). Cuando configura órbitas como extensiones virtuales, teléfonos móviles y teléfono RTC, no puede recuperar llamadas estacionadas.
  
Los usuarios asociados no pueden recuperar llamadas estacionadas.
  
Los siguientes clientes pueden recuperar llamadas que están estacionadas en el estacionamiento de llamadas:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- Teléfonos IP de área común
    
- Teléfonos que no son IP conectados a la infraestructura de Skype Empresarial Server, incluidos los teléfonos de área común y los teléfonos de central de conmutación (PBX).
    
## <a name="call-park-capacity-planning"></a>Planeación de la capacidad del estacionamiento de llamadas

En la tabla siguiente se describe el modelo de usuario estacionamiento de llamadas que puede usar como base para los requisitos de planeación de capacidad.
  
> [!IMPORTANT]
> Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debe poder controlar las cargas de trabajo para los servicios de estacionamiento de llamadas en ambos grupos. 
  
**Modelo de usuario de estacionamiento de llamadas**

|**Métrica**|**Por grupo de servidores front-end  <br/>  (con 8 servidores front-end)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Tasa de estacionamiento  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Recuperar la tasa de llamadas estacionadas  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Duración media del estacionamiento  <br/> |60 segundos  <br/> |60 segundos  <br/> |
   

