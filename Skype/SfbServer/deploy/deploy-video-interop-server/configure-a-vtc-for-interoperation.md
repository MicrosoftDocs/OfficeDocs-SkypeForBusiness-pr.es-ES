---
title: Configurar un VTC para la interoperabilidad con Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumen: Configure los dispositivos de VTC para que funcionen con Skype empresarial Server.'
ms.openlocfilehash: 8c5310479aea38f5623f8ac2e10ef64978aa4aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235676"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurar un VTC para la interoperabilidad con Skype empresarial Server
 
**Resumen:** Configure los dispositivos de VTC para que funcionen con Skype empresarial Server.
  
Tendrá que realizar los siguientes procedimientos de personalización de la configuración para cada VTC que se conecte al servidor de Skype empresarial VIS a través de un tronco de SIP y una puerta de enlace de vídeo Cisco Unified Communications Manager (CallManager o CUCM).
  
La configuración aquí descrita solo se refería como ejemplos de cómo se puede configurar CUCM para trabajar con VIS. Se puede recurrir a otras configuraciones o a otros usos de funciones de CUCM distintas para lograr el mismo resultado. Este documento no tiene que tomarse como una recomendación de configuración óptima para un escenario en particular.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurar un VTC registrado con CUCM

1. Inicie sesión en el dispositivo Cisco VTC y vaya a configuración-\>sistema de configuración\>-aprovisionamiento.
    
2. Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias): 
    
   |**Parámetro**|**Configuración recomendada**|
   |:-----|:-----|
   |Modo de aprovisionamiento  <br/> | CUCM <br/> |
   |Dirección del administrador externo  <br/> | FQDN de CUCM <br/> |
   | Dominio de ExternalManager <br/> |Dominio de CUCM  <br/> |
   
3. Vaya a configuración:\>configuración del sistema\>-red.
    
4. Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias): 
    
   |**Parámetro**|**Configuración recomendada**|
   |:-----|:-----|
   |Nombre de dominio DNS  <br/> | Nombre de dominio de CUCM <br/> |
   |Dirección 1 del servidor DNS  <br/> | Su dirección del servidor DNS <br/> |
   
5. Vaya a configuración:\>configuración del sistema\>-servicios de red. Asegúrese de que el modo H.323 está desactivado y de que el modo SIP está activado. 
    
6. Estas opciones se establecen automáticamente cuando el extremo se registra con CUCM. Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias): 
    
   |**Parámetro**|**Configuración recomendada**|
   |:-----|:-----|
   |Modo H.323  <br/> | Desactivado <br/> |
   |Modo HTTP  <br/> | Activado <br/> |
   | Modo SIP <br/> | Activado <br/> |
   |Modo Telnet  <br/> | Activado <br/> |
   |Texto de bienvenida  <br/> | Activado <br/> |
   |Modo XMLAPI  <br/> | Activado <br/> |
   
7. Vaya a configuración:\>configuración del sistema\>-SIP.
    
8. Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias): 
    
   |**Parámetro**|**Configuración recomendada**|
   |:-----|:-----|
   |Perfil 1: DefaultTransport  <br/> | TCP <br/> |
   |Perfil 1: Outbound  <br/> | Desactivado <br/> |
   |Perfil 1-TlsVerify  <br/> | Activado <br/> |
   |Perfil 1: Type  <br/> | Cisco <br/> |
   |Perfil 1: URI  <br/> | Asignado automáticamente al registrar CUCM <br/> |
   |Proxy 1: Address  <br/> |Nombre de host de CUCM  <br/> |
   
El VTC ya está registrado para interoperar. Para iniciar el servicio, necesitará realizar algunos pasos finales en CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurar dispositivos VTC en CUCM

1. Inicie sesión en CUCM y vaya a administración de CM unificada\>de Cisco\>-dispositivo\>-teléfono-buscar. 
    
2. Seleccione el dispositivo VTC que quiera configurar. Compruebe las siguientes configuraciones en la pantalla Configuración del teléfono (corrigiendo las que considere necesarias). Tras cambiar o confirmar las configuraciones, haga clic en **Guardar**.
    
   |**Parámetro**|**Configuración recomendada**|
   |:-----|:-----|
   |Información del dispositivo: plantilla de botón de teléfono  <br/> | Códec de telepresencia estándar de C40 <br/> |
   |Información del dispositivo: perfil de teléfono común  <br/> | Perfil de teléfono común estándar <br/> |
   |Información del dispositivo: espacio de búsqueda de llamadas  <br/> | CSS_SfBVideoInterop <br/> |
   |Información del dispositivo: espacio de búsqueda de llamadas AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Información del dispositivo: lista del grupo de los recursos del medio  <br/> | MRGL_SfBVideoInterop <br/> |
   |Información específica del protocolo: perfil de seguridad del dispositivo  <br/> | Códec de Telepresencia de Cisco C40 <br/> |
   |Información específica del protocolo: espacio de búsqueda de llamadas de reenrutamiento  <br/> | CSS_SfBVideoInterop <br/> |
   |Información específica de protocolo: SUSCRIBIrse a espacio de búsqueda de llamadas  <br/> | CSS_SfBVideoInterop <br/> |
   |Información específica del protocolo: perfil SIP  <br/> | Perfil SIP estándar para el extremo de telepresencia <br/> |
   
3. Una vez que haya guardado la configuración de VTC, vaya de nuevo a la pantalla de configuración del teléfono para el dispositivo. En la parte superior de la pantalla, en el grupo Asociación, haga clic en la asociación para la interoperabilidad del vídeo. De este modo se abrirá la pantalla Configuración de número de directorio. 
    
4. Compruebe las siguientes configuraciones (corrigiendo las que considere necesarias): 
    
    Realice los cambios pertinentes en Información de números de directorio y Configuración de números de directorio como se indica.
    
   |**Parámetro**|**Configuración recomendada**|
   |:-----|:-----|
   | Información de números de directorio: partición de enrutamiento <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Configuración de números de directorio: espacio de búsqueda de llamadas  <br/> | CSS_SfBVideoInterop <br/> |
   |Configuración de nivel de acceso confidencial y de parte alternativa de MLPP: espacio de búsqueda de llamadas de MLPP  <br/> | CSS_SfBVideoInterop <br/> |
   |Línea 1 en el dispositivo: Mostrar (identificación de llamadas)  <br/> | Según prefiera <br/> |
   |Línea 1 en el dispositivo: pantalla en ASCII (identificación de llamadas)  <br/> | Según prefiera <br/> |
   
5. Cuando termine, vaya a la parte superior de la pantalla y presione **Guardar**. 
    
De este modo, habrá completado la configuración de este dispositivo VTC. Este proceso tendrá que repetirse con cada dispositivo VTC de la compañía.

