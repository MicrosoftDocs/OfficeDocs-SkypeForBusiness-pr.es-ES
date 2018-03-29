---
title: Planificar el estacionamiento de llamadas en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planificación para el parque de llamada en Skype para Telefonía IP empresarial de Business Server, que permite poner llamadas en espera y transferencia de llamadas a los departamentos. Incluye el planeamiento de capacidad, llamadas admitidas y clientes admitidos.
ms.openlocfilehash: 6198b54a93c36c2e6a2fcd28fa91f51c43fb59de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-park-in-skype-for-business-2015"></a>Planificar el estacionamiento de llamadas en Skype Empresarial Server 2015
 
Planificación para el parque de llamada en Skype para Telefonía IP empresarial de Business Server, que permite poner llamadas en espera y transferencia de llamadas a los departamentos. Incluye el planeamiento de capacidad, llamadas admitidas y clientes admitidos.
  
La aplicación de llamada parque permite a los usuarios de Telefonía IP empresarial hacer lo siguiente:
  
- Poner una llamada en espera y recuperar la llamada desde el mismo teléfono o desde otro.
    
- Poner una llamada en espera para transferirla a un departamento o área general, por ejemplo, a un departamento de ventas o a un almacén donde hay un teléfono de área común.
    
- Poner una llamada en espera y conservar el teléfono original que ha respondido disponible para recibir otras llamadas.
    
Cuando un parques de usuario una llamada, Skype para Business Server transfiere la llamada a un número temporal, denominada una órbita, donde se mantiene la llamada hasta que se recuperan o se agota el tiempo. Skype para Business Server envía la órbita al usuario que haya aparcado la llamada. Para recuperar la llamada estacionada, el usuario puede marcar el número de órbita o hacer clic en el botón o vínculo de órbita de la ventana Conversación. 
  
El usuario que estacionó una llamada puede notificar a alguien que recupere la llamada usando un mecanismo externo, como la mensajería instantánea (MI) o un sistema de localización, para comunicar el número de órbita a otro usuario. El usuario que estacionó la llamada puede dejar la ventana Conversación abierta para recibir una notificación cuando se recupere la llamada.
  
Porque órbita rangos son globalmente únicos, es posible recuperar llamadas en cualquier Skype para sitio Business Server o teléfono PBX si el enrutamiento está configurado correctamente. Si nadie recupera la llamada en un período de tiempo configurable, la llamada volverá a sonar para la persona que la estacionó. Si dicha persona no responde esta vez, la llamada se transferirá a un destino de conmutación por error, como un operador, si se ha configurado así. Puedes configurar el número de veces que deseas que suene la llamada antes de ser transferida de una a diez veces. Si nadie responde a una llamada transferida, la llamada se desconectará. La órbita se libera cuando se recupera la llamada o se desconecta.
  
Al implementar el estacionamiento de llamadas, necesitarás reservar intervalos de números de extensión para estacionar llamadas. Estas extensiones necesitan ser extensiones virtuales: extensiones que no tienen ningún usuario o teléfono asignado. Luego, necesitarás configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión y especificar qué servicio de aplicaciones hospeda la aplicación Estacionamiento de llamadas que administra cada intervalo. Cada grupo de servidores Front-End tiene una tabla llamada Park correspondiente nuevo servidor de fondo que se utiliza para administrar las llamadas que se encuentra estacionadas en el grupo. La lista de rangos de órbita se almacena en la Administración Central almacenar y se utiliza para enrutar las órbitas al grupo de destino. Cada Skype para el grupo de servidores de empresa donde se ha implementado y configurada la aplicación llamada Park puede tener uno o más rangos de órbita. Rangos de órbita deben ser exclusivos globalmente en el Skype para la implementación de Business Server. 
  
También configuras otras opciones de estacionamiento de llamadas, como, por ejemplo, el lugar al que se redirigirán las llamadas si transcurre el tiempo de espera y si la persona que está al teléfono oirá música mientras la llamada está estacionada. Asimismo, puedes especificar el archivo de música que deseas que se reproduzca mientras la llamada está en espera.
  
> [!NOTE]
> Archivos de música en espera personalizados para el parque de llamada no se copia como parte de la Skype para el proceso de recuperación de desastres de Business Server y se perderán si están dañados, dañados o borrados los archivos cargados en el grupo. Guarda siempre una copia de seguridad independiente de los archivos de música en espera personalizados que haya cargado para el estacionamiento de llamadas. 
  
La aplicación Estacionamiento de llamadas es un componente de la telefonía IP empresarial. Al implementar la Telefonía IP empresarial, la aplicación de llamada Park es instalada y activada automáticamente. Para poder utilizar llamada Park, sin embargo, el Administrador de Telefonía IP empresarial debe configurarlo y habilitarlo para los usuarios a través de la directiva de voz.
  
## <a name="deployment-and-requirements"></a>Requisitos e implementación

La aplicación de llamada Park se instala automáticamente al implementar la Telefonía IP empresarial. Habilitar parque de llamada mediante la configuración de directiva de voz.
  
### <a name="software-requirements"></a>Requisitos de software

Todos los servidores frontales y Standard Edition de los servidores donde se implementa el parque de llamada deben tener instalado en servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecutan Windows Server 2012 o Windows Server Windows Media Format Runtime R2 DE 2012. Para Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows. Windows Media Format Runtime o Microsoft Media Foundation es necesario para Windows Media Audio (.wma) archivos llamada Park reproduce música en espera.
  
### <a name="port-requirements"></a>Requisitos de los puertos

La aplicación de llamada Park utiliza **5075 de puerto** para solicitudes de escucha de SIP.
    
> [!NOTE]
> Este puerto es una configuración predeterminada que se puede cambiar mediante el cmdlet **Set-CsApplicationServer** . Para obtener más información acerca de este cmdlet, vea la documentación del Shell de administración de Lync Server.
  
### <a name="audio-file-requirements"></a>Requisitos de archivos de audio

Mantenga la aplicación sólo admite Windows Media Audio (.wma) archivos de música en el parque de llamada. Puedes usar Microsoft Expression Encoder 4 para personalizar los archivos para la música en espera. Para descargar Expression Encoder 4, vea ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Usa la herramienta para convertir el archivo en un formato .wma. El formato recomendado para los archivos de música en espera de llamada Park es Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.
  
> [!NOTE]
> El archivo convertido se reproduce por el teléfono solo a 16 kHz, aunque se grabó a 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Llamadas y clientes compatibles

Se admiten los siguientes clientes y tipos de llamadas para el parque de llamada
  
### <a name="clients-supported-for-parking-calls"></a>Clientes compatibles con el estacionamiento de llamadas

Se pueden estacionar las llamadas de cualquier IP, central de conmutación (PBX), red telefónica conmutada (RTC) o teléfono móvil.
  
> [!NOTE]
> Únicamente se pueden estacionar las llamadas de audio. No se pueden estacionar los mensajes instantáneos ni las conferencias. 
  
Los siguientes clientes pueden utilizar parque de llamada para llamadas de park:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Operador de Skype Empresarial
    
- Lync Phone Edition
    
> [!NOTE]
> Teléfonos móviles no puede utilizar parque de llamada para llamadas de park. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clientes compatibles con la recuperación de llamadas

Los intervalos de órbitas están configurados como bloques de extensiones virtuales (extensiones sin ningún usuario ni teléfono asignado). Cuando configuras órbitas como extensiones virtuales, teléfonos móviles y teléfono RTC, no puedes recuperar llamadas estacionadas.
  
Los usuarios federados no pueden recuperar llamadas estacionadas.
  
Los siguientes clientes pueden recuperar llamadas que estén estacionadas en el parque de llamada:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Operador de Skype Empresarial
    
- Lync Phone Edition
    
- Teléfonos IP de área común
    
- No-IP teléfonos que están conectados con el Skype para infraestructura de Business Server, incluidos los teléfonos de área común y teléfonos de private branch exchange (PBX)
    
## <a name="call-park-capacity-planning"></a>Planificación de la capacidad del estacionamiento de llamadas

La tabla siguiente describe el modelo de usuario llamada Park que sirve como base para los requerimientos de planificación de capacidad.
  
> [!IMPORTANT]
> Tenga en cuenta que, para la planificación de capacidad del recuperación de desastres, cada grupo de un grupo de par debe ser capaz de manejar las cargas de trabajo para los servicios de llamada parque de ambos grupos. 
  
**Modelo de usuario llamada Park**

|**Métrica**|**Por cada grupo de Front-End <br/> (con 8 servidores frontales)**|**Por cada servidor Standard Edition**|
|:-----|:-----|:-----|
|Tasa de estacionamiento  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Tasa de recuperación de llamadas estacionadas  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Promedio de duración del estacionamiento  <br/> |60 segundos  <br/> |60 segundos  <br/> |
   

