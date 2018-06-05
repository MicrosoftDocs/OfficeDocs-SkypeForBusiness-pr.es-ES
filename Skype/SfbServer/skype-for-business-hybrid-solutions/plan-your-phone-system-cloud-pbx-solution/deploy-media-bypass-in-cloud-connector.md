---
title: Implementar el desvío de medios en la nube conector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lea este tema para obtener información acerca de los pasos para implementar el desvío de medios con la nube conector Edition versión 2.0 y versiones posterior.
ms.openlocfilehash: 0d147cbd1f6497757aa73e380ebeca0c03f1de7b
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19505198"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Implementar el desvío de medios en la nube conector Edition
 
Lea este tema para obtener información acerca de los pasos para implementar el desvío de medios con la nube conector Edition versión 2.0 y versiones posterior. 
  
Desvío de medios permite que un cliente enviar medios directamente en el próximo salto pública red de telefónica conmutada (RTC): una puerta de enlace o el controlador de borde de sesión (SBC) — y eliminar el componente de edición de conector en la nube desde la ruta de acceso de medios. Vea también [Plan para los medios de desvío en la nube conector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Habilitar omisión de medios

Para habilitar el desvío de medios, debe configurar el nombre DNS del servicio web de desvío de medios y activar el desvío de medios en la configuración del inquilino. El servicio web de desvío de medios se implementa automáticamente en cada servidor de mediación. Un administrador de inquilinos debe elegir un nombre para un servicio de voz híbrida (sitio) y este nombre debe ser de un dominio SIP registrado para voz híbrida. El nombre del servicio debe ser el mismo en todos los dispositivos de conector en la nube y todos los sitios de RTC, independientemente de la ubicación del cliente. El servicio web sólo debe estar disponible internamente en la red.
  
Un administrador de inquilinos debe configurar un registro A DNS en Active Directory de producción interna. Si tiene un entorno complejo de varios sitio, vea el ejemplo en [ejemplo: registros DNS del sitio web en entornos de varios sitios complejos de desvío de medios](deploy-media-bypass-in-cloud-connector.md#Example). Sólo debe resolver el registro de DNS para los clientes de la red interna; no se debe resolver para los clientes de la red externa.
  
Después de configurar DNS, conectarse a Skype para profesionales Online mediante PowerShell remoto con Skype las credenciales de administrador empresarial. Para obtener más información, consulte [Connecting to Skype para profesionales en línea mediante Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
En la sesión de PowerShell, introduzca los siguientes comandos para habilitar la omisión de medios:
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Habilitar desvío de medios es un proceso de dos pasos. El cmdlet New-CsNetworkMedia no guardar inmediatamente la nueva configuración; sólo se crea la configuración en la memoria. El objeto creado por este cmdlet debe ser guardado en una variable y, a continuación, se asigna a la propiedad MediaBypassSettings de la configuración de red. Para obtener más información, vea [ejemplo: registros DNS del sitio web en entornos de varios sitios complejos de desvío de medios](deploy-media-bypass-in-cloud-connector.md#Example).
  
La replicación entre los componentes en línea y local puede tardar hasta 24 horas, por lo que Microsoft recomienda que ejecutar los comandos necesarios antes de habilitar a los usuarios.
  
## <a name="confirm-media-bypass-settings"></a>Confirmar la configuración de la omisión de medios

La configuración de la omisión de medios se puede comprobar de la siguiente manera.  
  
Para comprobar la replicación en línea al grupo de servidores de inquilinos, ejecute el siguiente comando en PowerShell remoto:
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

Para comprobar la replicación local, conectarse a los servidores de mediación de conector en la nube, ejecute el siguiente comando en PowerShell y confirme que Enabled = True y AlwaysBypass = True
  
```
Get-CsNetworkConfiguration -LocalStore
```

Para comprobar la configuración del cliente, desconectarse de la Skype para clientes empresariales, vuelva a iniciarla y confirme que el cliente ha recibido la dirección URL del servicio como se indica a continuación:
  
1. Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.  
    
2. Buscar hybridconfigserviceinternalurl y confirme la dirección URL coincide con el que haya definido.
    
## <a name="change-media-bypass-parameters"></a>Cambiar los parámetros de la omisión de medios

Los administradores de inquilinos pueden modificar el nombre DNS del servicio web mediante la ejecución del siguiente cmdlet:
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Los clientes tienen que cerrar la sesión y volver a iniciarla para obtener el nombre nuevo del servicio y reconocer el cambio.  
  
## <a name="temporarily-disable-media-bypass"></a>Deshabilitar temporalmente la omisión de medios

Este escenario puede ser útil para solucionar problemas o como mantenimiento. Para deshabilitar el servicio, ejecute los siguientes cmdlet:
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Después de realizar el cambio, podría tardar algún tiempo para que los cambios en replicarse en todos los conectores de la nube. Para comprobar el estado de replicación, ejecute el siguiente cmdlet de PowerShell en los servidores de mediación de conector en la nube: 
  
```
Get- CsNetworkConfiguration -LocalStore
```

Una vez que se repliquen los cambios, el servicio web del servidor de mediación comenzará a rechazar las solicitudes del cliente para el servicio de omisión de medios.
  
## <a name="disable-media-bypass-permanently"></a>Deshabilitar permanentemente la omisión de medios

Para deshabilitar permanentemente la omisión de medios, un administrador de inquilinos debe ejecutar los siguientes comandos:  
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un administrador también necesitará quitar las direcciones de web para el desvío de medios de servidores DNS internos. Después de realizar el cambio, podría tardar algún tiempo para que los cambios en replicarse a todos los dispositivos de conector en la nube. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Ejemplo: Los registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios
<a name="Example"> </a>

Los clientes recibirán la dirección web del servicio web de desvío de medios desde un servidor DNS interno. El nombre del servicio web será el mismo en todos los dispositivos de conector en la nube y sitios de RTC de conector en la nube. En un entorno complejo de varios sitio, se recomienda usar la directiva de DNS de 2016 de Windows para la administración de tráfico en función de ubicación geográfica, por lo que los clientes pueden redirigirse al servicio web que es local para su red. 
  
Para obtener más información acerca de las directivas de DNS de Windows 2016, vea [Use la directiva de DNS para la administración de tráfico en función de ubicación geográfica con servidores principales](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).
  
A continuación se muestra un ejemplo de configuración para un empresa con varios sitios mediante la directiva DNS de Windows 2016 para la geolocalización basada en la administración del tráfico.
  
El nombre para el servicio de desvío es 'hybridvoice.adatum.biz'.
  
El sitio en Ámsterdam tiene cuatro dispositivos de conector en la nube que se implementan con las siguientes direcciones IP de servidor de mediación:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
El sitio de Seattle tiene tres dispositivos de conector en la nube que implementan con las siguientes direcciones IP de servidor de mediación:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Con la geolocalización basada en la administración del tráfico, los servidores DNS se configurarían del siguiente modo:
  
1. Cree subredes de clientes DNS para las subredes de Ámsterdam y Seattle.
    
2. Cree los ámbitos de zona DNS para adatum.biz para Ámsterdam y Seattle.
    
3. Cree los registros DNS en cada ámbito de zona DNS.
    
    Ámsterdam
    
  - Tipo A
    
  - Nombre: hybridvoice en la zona DNS adatum.biz
    
  - Destino: 192.168.1.45
    
    Cree registros adicionales para los servidores de mediación adicionales
    
  - 192.168.1.46
    
  - 192.168.1.47
    
  - 192.168.1.48
    
    Seattle
    
  - Tipo A
    
  - Nombre: hybridvoice en la zona DNS adatum.biz
    
  - Destino: 10.10.1.8
    
    Cree registros adicionales para los servidores de mediación adicionales
    
  - 10.10.1.9
    
  - 10.10.1.10
    
4. Cree la directiva DNS que conecta las subredes del cliente con los ámbitos de zona apropiados para garantizar la resolución DNS que desea.
    
En este punto, los clientes que hagan consultas de DNS desde la subred de Ámsterdam para hybridvoice.adatum.biz devolverán las direcciones 192.168.1.45, 192.168.1.46, 192.168.1.47 y 192.168.1.48, mientras que los clientes que hagan la misma consulta desde Seattle devolverán 10.10.1.8, 10.10.1.9 y 10.10.1.10.
  
## <a name="see-also"></a>Vea también
<a name="Example"> </a>

[Planeación de desvío de medios en la nube conector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)