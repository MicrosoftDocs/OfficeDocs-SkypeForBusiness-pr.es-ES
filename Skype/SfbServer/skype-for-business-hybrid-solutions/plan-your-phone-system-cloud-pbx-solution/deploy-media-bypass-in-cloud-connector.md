---
title: Implementación de omisión de medios en Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lea este tema para obtener información sobre los pasos para implementar los elementos multimedia con la versión 2,0 y posteriores de Cloud Connector Edition.
ms.openlocfilehash: 63d8f9e289c38a50444bee2667c98543e09b875d
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003490"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Implementación de omisión de medios en Cloud Connector Edition
 
Lea este tema para obtener información sobre los pasos para implementar los elementos multimedia con la versión 2,0 y posteriores de Cloud Connector Edition. 
  
La omisión de elementos multimedia permite a un cliente enviar archivos directamente al próximo salto de la red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC), y eliminar el componente Cloud Connector Edition de la ruta multimedia. Consulte también el [plan de omisión de medios en Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Habilitar omisión de medios

Para habilitar la omisión de medios, debe configurar el nombre DNS del servicio web de omisión de medios y activar la omisión de medios en la configuración de inquilinos. El servicio web de omisión de medios se implementa automáticamente en cada servidor de mediación. Un administrador de inquilinos debe elegir un nombre para un servicio de voz híbrida (sitio) y este nombre debe provenir de un dominio SIP registrado para la voz híbrida. El nombre del servicio debe ser el mismo en todos los dispositivos de conexión en la nube y en todos los sitios RTC, independientemente de la ubicación del cliente. El servicio web solo debe estar disponible internamente en la red.
  
Un administrador de inquilinos debe configurar un registro DNS A en el Active Directory de producción interna. Si tiene un entorno complejo con varios sitios, vea el ejemplo en [ejemplo: multimedia omitir los registros DNS de un sitio web en entornos complejos con varios sitios](deploy-media-bypass-in-cloud-connector.md#Example). El registro DNS solo debe resolver la situación en el caso de clientes de red internos, no para clientes de red externos.
  
Tras configurar DNS, conecte Skype Empresarial Online mediante el PowerShell remoto con las credenciales del administrador de Skype Empresarial. Para obtener más información, vea [configurar el equipo para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
En la sesión de PowerShell, introduzca los siguientes comandos para habilitar la omisión de medios:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

El proceso para habilitar la omisión de medios consta de dos pasos. El cmdlet New-CsNetworkMedia no guarda la nueva configuración inmediatamente; solo la crea en la memoria. El objeto que crea este cmdlet se debe guardar en una variable y después se debe asignar a la propiedad MediaBypassSettings de la configuración de red. Para obtener más información, vea [ejemplo: multimedia omitir los registros DNS de un sitio web en entornos complejos con varios sitios](deploy-media-bypass-in-cloud-connector.md#Example).
  
La replicación entre los componentes locales y en línea puede tardar hasta 24 horas, por lo que Microsoft recomienda que ejecute los comandos necesarios antes de habilitar usuarios.
  
## <a name="confirm-media-bypass-settings"></a>Confirmar la configuración de la omisión de medios

La configuración de la omisión de medios se puede comprobar de la siguiente manera.  
  
Para comprobar la replicación en línea en el grupo de inquilinos, ejecute el siguiente comando en PowerShell remoto:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Para comprobar la replicación local, conéctese a los servidores de media de los conectores de nube, ejecute el siguiente comando en PowerShell y confirme que Enabled = true y AlwaysBypass = true
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Para comprobar la configuración del cliente, cierre sesión en el cliente de Skype empresarial, vuelva a iniciar sesión y confirme que el cliente ha recibido la dirección URL del servicio de la siguiente manera:
  
1. Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Busque hybridconfigserviceinternalurl y confirme que la dirección URL coincida con la que ha definido.
    
## <a name="change-media-bypass-parameters"></a>Cambiar los parámetros de la omisión de medios

Los administradores de inquilinos pueden modificar el nombre DNS del servicio web mediante la ejecución del siguiente cmdlet:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Los clientes tienen que cerrar la sesión y volver a iniciarla para obtener el nombre nuevo del servicio y reconocer el cambio.  
  
## <a name="temporarily-disable-media-bypass"></a>Deshabilitar temporalmente la omisión de medios

Este escenario puede ser útil para solucionar problemas o como mantenimiento. Para deshabilitar el servicio, ejecute los siguientes cmdlet:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Tras hacer el cambio, es posible que pase algún tiempo hasta que los cambios se repliquen en todas las instancias de Cloud Connector. Para comprobar el estado de la replicación, ejecute el siguiente cmdlet en PowerShell en los servidores de mediación del conector en la nube: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Una vez que se repliquen los cambios, el servicio web del servidor de mediación comenzará a rechazar las solicitudes del cliente para el servicio de omisión de medios.
  
## <a name="disable-media-bypass-permanently"></a>Deshabilitar permanentemente la omisión de medios

Para deshabilitar permanentemente la omisión de medios, un administrador de inquilinos debe ejecutar los siguientes comandos: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un administrador también tendrá que quitar las direcciones web para la omisión de medios de los servidores DNS internos. Después de realizar el cambio, los cambios pueden tardar algún tiempo en replicarse en todos los dispositivos de conexión en la nube. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Ejemplo: Los registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios
<a name="Example"> </a>

Los clientes recibirán la dirección web del servicio web de omisión de medios desde un servidor DNS interno. El nombre del servicio Web será el mismo en todos los equipos conector de nube y en los sitios RTC del conector de nube. En un entorno complejo de varios sitios, recomendamos que utilice la directiva DNS de Windows 2016 para la administración del tráfico basado en la geolocalización, de manera que se pueda redirigir a los clientes al servicio web que sea local para la red. 
  
Para obtener más información sobre las directivas DNS de Windows 2016, consulte [usar la Directiva DNS para la administración de tráfico basada en la ubicación geográfica con los servidores principales](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
A continuación se muestra un ejemplo de configuración para un empresa con varios sitios mediante la directiva DNS de Windows 2016 para la geolocalización basada en la administración del tráfico.
  
El nombre del servicio de derivación es ' hybridvoice.adatum.biz '.
  
El sitio de Amsterdam tiene cuatro dispositivos de conexión de nube implementados con las siguientes direcciones IP de servidor de mediación:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
El sitio de Seattle tiene tres dispositivos de conexión en la nube implementados con las siguientes direcciones IP del servidor de mediación:
  
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

> [!NOTE]
> Si el dispositivo de CCE no parece estar recibiendo la configuración actualizada, compruebe si el dispositivo puede ponerse en contacto con el inquilino a través de PowerShell remoto. Puede usar PowerShell remoto para comprobar el estado del equipo con get-CsHybridPSTNAppliance o usar PowerShell en el host de CCE para comprobar el estado con get-CcApplianceStatus.

  
## <a name="see-also"></a>Vea también
<a name="Example"> </a>

[Plan para la omisión de medios en Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
