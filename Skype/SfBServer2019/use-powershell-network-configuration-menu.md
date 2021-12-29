---
title: Usar PowerShell para tareas en el menú Configuración de red
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Resumen: Skype Empresarial Server panel de control a la asignación de cmdlets para el menú Configuración de red.'
ms.openlocfilehash: aa42ac465ffd72a4aff9c03293124c857e5b712c
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626520"
---
# <a name="network-configuration"></a>Configuración de la red

En este artículo se describe cómo  se pueden obtener resultados similares a los del elemento de menú Configuración de red en el Panel de control heredado mediante cmdlets.

En este artículo se describen los siguientes submenúes:

- [Configuración de red](#network-configuration)
  - [Directiva de ubicación](#location-policy)
  - [Directiva de ancho de banda](#bandwidth-policy)
  - [Región](#region)
  - [Site](#site)
  - [Subred](#subnet)
  - [Vínculo de región](#region-link)
  - [Ruta regional](#region-route)

## <a name="location-policy"></a>Directiva de ubicación

El **submenú LOCATION POLICY** se usa para aplicar la configuración relacionada con la funcionalidad E9-1-1. La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia.

Consideremos las distintas tareas que un usuario puede hacer en **LOCATION POLICY** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todas las directivas de ubicación

   ![Directiva de ubicación de lista](./media/location-policy-1.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Ejemplo***

```powershell
 Get-CsLocationPolicy
```

---

> **Escenario 2:** Crear una nueva directiva de ubicación

   ![Crear directiva de ubicación](./media/location-policy-2.png)

***Cmdlet***

[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy)  

***Ejemplo***

```powershell
 New-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

> **Escenario 3:** obtener detalles de una directiva de ubicación elegida

   ![Obtener directiva de ubicación](./media/location-policy-3.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Ejemplo***

```powershell
 Get-CsLocationPolicy -Identity Reno
```

---

> **Escenario 4:** Eliminar directivas de ubicación elegidas

   ![Eliminar directiva de ubicación](./media/location-policy-4.png)

***Cmdlet***

[Remove-CsLocationPolicy](/powershell/module/skype/remove-cslocationpolicy)

***Ejemplo***

```powershell
 Remove-CsLocationPolicy -Identity Reno
```

---

> **Escenario 5:** Actualizar una directiva de ubicación

   ![Actualizar directiva de ubicación](./media/location-policy-5.png)

***Cmdlet***

[Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy)

***Ejemplo***

```powershell
 Set-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

## <a name="bandwidth-policy"></a>Directiva de ancho de banda

Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades. (En Skype Empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo). Este cmdlet crea un perfil de contenedor para estas directivas. Al llamar a este cmdlet, defina las directivas individuales dentro del contenedor especificando las limitaciones de ancho de banda para audio y vídeo.

Consideremos las distintas tareas que un usuario puede hacer en **BANDWIDTH POLICY** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---
> **Escenario 1:** Enumerar todas las directivas de ancho de banda

   ![Directiva de ancho de banda de lista](./media/bandwidth-policy-1.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Ejemplo***

```powershell
 Get-CsNetworkBandwidthPolicyProfile
```

---

> **Escenario 2:** Crear una nueva directiva de ancho de banda

   ![Nueva directiva de ancho de banda](./media/bandwidth-policy-2.png)

***Cmdlet***

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile)  

***Ejemplo***

```powershell
 New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500
```

---

> **Escenario 3:** Obtener detalles de una directiva de ancho de banda elegida

   ![Obtener directiva de ancho de banda](./media/bandwidth-policy-3.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Ejemplo***

```powershell
 Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Escenario 4:** Eliminar directivas de ancho de banda elegidas

   ![Eliminar directiva de ancho de banda](./media/bandwidth-policy-4.png)

***Cmdlet***

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile)

***Ejemplo***

```powershell
 Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Escenario 5:** Actualizar una directiva de ancho de banda

   ![Actualizar directiva de ancho de banda](./media/bandwidth-policy-5.png)

***Cmdlet***

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile)

***Ejemplo***

```powershell
 Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300
```

---

## <a name="region"></a>Región

Una región de red interconecta varias partes de una red a través de varias zonas geográficas. Cada región de red debe asociarse con un sitio central. Los administradores pueden usar el menú **REGIÓN** para administrar información sobre una o más regiones de red, incluidos el sitio central asociado y la configuración que determinan si se permiten rutas alternativas para conexiones de audio y vídeo, y que asocian los sitios de la región con una configuración de desvío de medios.

---

> **Escenario 1:** Enumerar todas las regiones

   ![Región de lista](./media/network-region-1.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Ejemplo***

```powershell
 Get-CsNetworkRegion
```

---

> **Escenario 2:** Crear una nueva región

   ![Crear región](./media/network-region-2.png)

***Cmdlet***

[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion)  

***Ejemplo***

```powershell
 New-CsNetworkRegion -Identity NorthAmerica -Description "All North American Locations" -CentralSite Redmond-NA-MLS
```

---

> **Escenario 3:** Obtener detalles de una región elegida

   ![Obtener región](./media/network-region-3.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Ejemplo***

```powershell
 Get-CsNetworkRegion -Identity NorthAmerica
```

---

> **Escenario 4:** Eliminar regiones elegidas

   ![Eliminar región](./media/network-region-4.png)

***Cmdlet***

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion)

***Ejemplo***

```powershell
 Remove-CsNetworkRegion -Identity NorthAmerica
```

---

> **Escenario 5:** Actualizar una región

   ![Actualizar región](./media/network-region-5.png)

- **Anotación 1: resultado**

    Esta anotación en la imagen indica un resultado, es decir, los datos que se recuperan y se muestran.

    ***Cmdlet***

    [Get-CsNetworkSite from Region](/powershell/module/skype/get-csnetworksite)

    ***Ejemplo***

    ```powershell
     Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "AKR"}
    ```

- **Anotación 2: Opción (para el usuario)**

    Esta anotación en la imagen indica una opción para que el usuario implemente, es decir, para guardar una región de red.

    [Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion)

   ***Ejemplo***

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"
   ```

---

## <a name="site"></a>Site

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de E9-1-1 o CAC. **El** submenú SITE ayuda a los administradores a agregar, quitar o administrar su configuración.

Consideremos las distintas tareas que un usuario puede hacer en **SITE** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todos los sitios

   ![Sitio de lista](./media/network-site-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Ejemplo***

```powershell
 Get-CsNetworkSite
```

---

> **Escenario 2:** Crear un sitio nuevo

   ![Crear sitio](./media/network-site-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksite)  

***Ejemplo***

```powershell
 New-CsNetworkSite -Identity Vancouver -NetworkRegionID NorthAmerica
```

---

> **Escenario 3:** Obtener detalles de un sitio elegido

   ![Obtener sitio](./media/network-site-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Ejemplo***

```powershell
 Get-CsNetworkSite -Identity Redmond
```

---

> **Escenario 4:** Eliminar sitios elegidos

   ![Eliminar sitio](./media/network-site-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksite)

***Ejemplo***

```powershell
 Remove-CsNetworkSite -Identity Vancouver
```

---

> **Escenario 5:** Actualizar un sitio

   ![Actualizar sitio](./media/network-site-5.png)

- **Anotación 1: resultado**

    Esta anotación en la imagen indica un resultado, es decir, los datos que se recuperan y se muestran.

    ***Cmdlet***

    [Get-CsNetworkSubnet desde el sitio](/powershell/module/skype/get-csnetworksubnet)

    ***Ejemplo***

    ```powershell
     Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"}
    ```

- **Anotación 2: Opción (para el usuario)**

    Esta anotación en la imagen indica una opción para que el usuario implemente, es decir, guardar un sitio de red.

   ***Cmdlet***

   [Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksite)

   ***Ejemplo***

   ```powershell
    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits
   ```

---

## <a name="subnet"></a>Subred

Los administradores pueden usar el submenú **SUBNET** para crear, actualizar y administrar subredes de red.

Consideremos las distintas tareas que un usuario puede hacer en **SUBNET** y los cmdlets Skype Empresarial a las que se asignan esas tareas.

---

> **Escenario 1:** Enumerar todas las subredes

   ![Subred de lista](./media/network-subnet-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Ejemplo***

```powershell
 Get-CsNetworkSubnet
```

---

> **Escenario 2:** Crear una nueva subred

   ![Crear subred](./media/network-subnet-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet)  

***Ejemplo***

```powershell
 New-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 24 -NetworkSiteID Vancouver
```

---

> **Escenario 3:** Obtener detalles de una subred elegida

   ![Obtener subred](./media/network-subnet-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Ejemplo***

```powershell
 Get-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Escenario 4:** Eliminar subredes elegidas

   ![Eliminar subred](./media/network-subnet-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet)

***Ejemplo***

```powershell
 Remove-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Escenario 5:** Actualizar una subred

   ![Actualizar subred](./media/network-subnet-5.png)

***Cmdlet***

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet)

***Ejemplo***

```powershell
 Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago
```

---

## <a name="region-link"></a>Vínculo de región

Las regiones dentro de una red están vinculadas a través de la conectividad WAN física. Los administradores pueden usar el submenú **REGION LINK** para crear, actualizar y administrar subredes de red.

Consideremos las distintas tareas que un usuario puede hacer en **REGION LINK** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todos los vínculos de región

   ![Vínculo de región de lista](./media/network-regionlink-1.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Ejemplo***

```powershell
 Get-CsNetworkRegionLink
```

---

> **Escenario 2:** Crear un nuevo vínculo de región

   ![Crear vínculo de región](./media/network-regionlink-2.png)

***Cmdlet***

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionLink)  

***Ejemplo***

```powershell
 New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits
```

---

> **Escenario 3:** Obtener detalles de un vínculo de región elegido

   ![Obtener vínculo de región](./media/network-regionlink-3.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Ejemplo***

```powershell
 Get-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Escenario 4:** Eliminar vínculos de región elegidos

   ![Eliminar vínculo de región](./media/network-regionlink-4.png)

***Cmdlet***

[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionLink)

***Ejemplo***

```powershell
 Remove-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Escenario 5:** Actualizar un vínculo de región

   ![Actualizar vínculo de región](./media/network-regionlink-5.png)

***Cmdlet***

[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionLink)

***Ejemplo***

```powershell
 Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits
```

---

## <a name="region-route"></a>Ruta regional

Cada región dentro de una configuración CAC debe tener alguna forma de obtener acceso a todas las otras regiones. Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y además representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra. Los administradores pueden usar el submenú **REGION ROUTE** para crear, actualizar y administrar estos.

Consideremos las distintas tareas que un usuario puede hacer en **REGION ROUTE** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todas las rutas regionales

   ![Enumerar ruta de región](./media/network-regionroute-1.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Ejemplo***

```powershell
 Get-CsNetworkInterRegionRoute
```

---

> **Escenario 2:** Crear una nueva ruta de región

   ![Crear ruta de región](./media/network-regionroute-2.png)

***Cmdlet***

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute)  

***Ejemplo***

```powershell
 New-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA_EMEA,EMEA_APAC"
```

---

> **Escenario 3:** Obtener detalles de una ruta de región elegida

   ![Obtener ruta de región](./media/network-regionroute-3.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Ejemplo***

```powershell
 Get-CsNetworkInterRegionRoute -Filter *APAC*
```

---

> **Escenario 4:** Eliminar rutas de región elegidas

   ![Eliminar ruta de región](./media/network-regionroute-4.png)

***Cmdlet***

[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute)

***Ejemplo***

```powershell
 Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route
```

---

> **Escenario 5:** Actualizar una ruta de región

   ![Actualizar ruta de región](./media/network-regionroute-5.png)

- **Anotación 1: Opción (para el usuario)**

    Esta anotación en la imagen indica un resultado, es decir, los datos que se recuperan y se muestran.

   ***Cmdlet***

   [Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

   ***Ejemplo***

   ```powershell
   Get-CsNetworkRegionLink
   ```

- **Anotación 2: Opción (para el usuario)**

    Esta anotación en la imagen indica una opción para que el usuario implemente, es decir, guardar una ruta de región de red.

    ***Cmdlet***

   [Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute)

   ***Ejemplo***

   ```powershell
   Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"
   ```

---
---
