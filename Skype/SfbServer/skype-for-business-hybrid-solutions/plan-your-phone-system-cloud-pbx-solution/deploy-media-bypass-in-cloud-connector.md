---
title: Implementar la omisión de medios en nube conector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lea este tema para conocer los pasos para implementar omisión de medios con conector de nube Edition versión 2.0 y versiones posterior.
ms.openlocfilehash: a9f03d1d83d398a6aa78f90a4741d0010ea50392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Implementar la omisión de medios en nube conector Edition
 
Lea este tema para conocer los pasos para implementar omisión de medios con conector de nube Edition versión 2.0 y versiones posterior. 
  
Omisión de medios permite que un cliente envíe medios directamente en el próximo salto de red pública de telefónica conmutada (PSTN), un gateway o un controlador de borde de sesión (SBC) y eliminar el componente de edición de conector de nube desde la ruta de acceso de medios. Vea también [Plan para medios de derivación en nube conector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Habilitar omisión de medios

Para habilitar la omisión de medios, debe configurar el nombre DNS del servicio web de omisión de los medios de comunicación y activar la omisión de medios en la configuración de inquilinos. El servicio web de omisión de medios se despliega automáticamente en cada servidor de mediación. Un administrador de inquilinos debe elegir un nombre para un servicio de voz híbrida (sitio) y este nombre debe ser de un dominio SIP registrado para voz híbrida. El nombre del servicio debe ser el mismo en todos los dispositivos de conector de nube y todos los sitios PSTN independientemente de la ubicación del cliente. El servicio web sólo debe estar disponible internamente en la red.
  
Un administrador de inquilinos debe configurar un registro A DNS en Active Directory de producción interna. Si tiene un entorno complejo de múltiples sitios, vea el ejemplo en [ejemplo: media omitir registros DNS del sitio web en entornos de múltiples sitios complejos](deploy-media-bypass-in-cloud-connector.md#Example). Sólo debe resolver el registro DNS para los clientes de la red interna; no se deben resolver para los clientes de la red externa.
  
Después de configurar DNS, conectarse a Skype para los negocios en línea mediante PowerShell remoto con Skype las credenciales de administrador de empresa. Para obtener más información, vea [Conectar con Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
En la sesión de PowerShell, introduzca los siguientes comandos para habilitar la omisión de medios:
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Habilitar omisión de medios es un proceso de dos pasos. El cmdlet New-CsNetworkMedia no guardar inmediatamente la nueva configuración; sólo crea la configuración en la memoria. El objeto creado mediante este cmdlet debe guardar en una variable y, a continuación, se asigna a la propiedad MediaBypassSettings de la configuración de red. Para obtener más información, consulte [ejemplo: media omitir registros DNS del sitio web en entornos de múltiples sitios complejos](deploy-media-bypass-in-cloud-connector.md#Example).
  
La replicación entre el local y de los componentes en línea puede tardar hasta 24 horas, lo que Microsoft recomienda ejecutar los comandos necesarios antes de permitir a los usuarios.
  
## <a name="confirm-media-bypass-settings"></a>Confirmar la configuración de la omisión de medios

La configuración de la omisión de medios se puede comprobar de la siguiente manera.  
  
Para comprobar la replicación en línea de la agrupación de inquilinos, ejecute el siguiente comando en PowerShell remoto:
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

Para comprobar la replicación local, conectar a los servidores de mediación de conector de nube, ejecute el siguiente comando en PowerShell y confirmar que Enabled = True y AlwaysBypass = True
  
```
Get-CsNetworkConfiguration -LocalStore
```

Para comprobar la configuración del cliente, cerrar la sesión de la Skype para Business client, volver a iniciarla y confirme que el cliente ha recibido la dirección URL del servicio como sigue:
  
1. Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.  
    
2. Buscar hybridconfigserviceinternalurl y confirmar la dirección URL coincide con la que ha definido.
    
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

Tras realizar el cambio, puede llevar algún tiempo para cambios en replicarse en todos los conectores de nube. Para comprobar el estado de la replicación, ejecute el siguiente cmdlet de PowerShell en servidores de mediación de conector de nube: 
  
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

También será necesario un administrador quitar las direcciones web de omisión de medios de servidores DNS internos. Tras realizar el cambio, puede llevar algún tiempo para cambios en replicarse en todos los dispositivos de conector de nube. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Ejemplo: Los registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios
<a name="Example"> </a>

Los clientes recibirán la dirección web del servicio web de omisión de medios desde un servidor DNS interno. El nombre del servicio web será el mismo en todos los dispositivos de conector de nube y sitios de nube conector PSTN. En un entorno complejo de múltiples sitios, se recomienda utilizar Directiva de 2016 de DNS de Windows para gestionar el tráfico según ubicación geográfica, por lo que los clientes pueden redirigirse al servicio web que es para su red local. 
  
Para obtener más información acerca de las directivas de Windows 2016 DNS, vea [Utilizar DNS directivas para gestionar el tráfico según ubicación geográfica con servidores principales](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).
  
A continuación se muestra un ejemplo de configuración para un empresa con varios sitios mediante la directiva DNS de Windows 2016 para la geolocalización basada en la administración del tráfico.
  
El nombre del servicio de derivación es 'hybridvoice.adatum.biz'.
  
El sitio en Amsterdam tiene cuatro dispositivos de nube conector implementadas con las siguientes direcciones IP de servidor de mediación:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
El sitio de Seattle tiene tres dispositivos de nube conector implementadas con las siguientes direcciones IP de servidor de mediación:
  
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

#### 

[Planear la omisión de medios en nube conector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

