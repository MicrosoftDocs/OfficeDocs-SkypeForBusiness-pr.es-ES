---
title: Configurar un VTC para interoperación con Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumen: configure los dispositivos VTC para que funcionen con Skype Empresarial Server.'
ms.openlocfilehash: 0c96766daf67ff3c8f7872a75423f64f64acba8e51d3fbc4c0edef841cc529e6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307781"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurar un VTC para interoperación con Skype Empresarial Server
 
**Resumen:** Configure los dispositivos VTC para que funcionen con Skype Empresarial Server.
  
Deberá realizar los siguientes procedimientos de personalización de configuración para cada VTC que se conectará al servidor VIS de Skype Empresarial a través de un tronco SIP y una puerta de enlace de vídeo del Administrador de comunicaciones unificadas de Cisco (CallManager o CUCM).
  
Las configuraciones descritas aquí están pensadas solo como ejemplos de cómo CUCM puede configurarse para funcionar con un VIS. También se podrían usar otras configuraciones o usos de la funcionalidad cucm alternativa para lograr el mismo resultado. No se recomienda la configuración óptima para un escenario determinado.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurar un VTC registrado con CUCM

1. Inicie sesión en el dispositivo VTC de Cisco y vaya a Configuración- \> Configuración del sistema- \> Aprovisionamiento.
    
2. Compruebe la siguiente configuración, corrigiéndola según sea necesario: 
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Modo de aprovisionamiento  <br/> | CUCM <br/> |
   |Dirección de ExternalManager  <br/> | FQDN de CUCM <br/> |
   | Dominio de ExternalManager <br/> |Dominio de CUCM  <br/> |
   
3. Vaya a Configuración- \> Configuración del sistema- \> Red.
    
4. Compruebe la siguiente configuración, corrigiéndola según sea necesario: 
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Nombre de dominio DNS  <br/> | Nombre de dominio de CUCM <br/> |
   |Dirección del servidor DNS 1  <br/> | la dirección del servidor DNS deseada <br/> |
   
5. Vaya a Configuración- \> Configuración del sistema: \> Servicios de red. Asegúrese de que el modo H.323 está desactivado y que el modo SIP está activado. 
    
6. Estas opciones se establecen automáticamente cuando el extremo está registrado con CUCM. Compruebe la siguiente configuración, corrigiéndola según sea necesario: 
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Modo H.323  <br/> | Desactivado <br/> |
   |Modo HTTP  <br/> | Activado <br/> |
   | Modo SIP <br/> | Activado <br/> |
   |Modo Telnet  <br/> | Activado <br/> |
   |WelcomeText  <br/> | Activado <br/> |
   |Modo XMLAPI  <br/> | Activado <br/> |
   
7. Vaya a Configuración- \> Configuración del sistema- \> SIP.
    
8. Compruebe la siguiente configuración, corrigiéndola según sea necesario: 
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Perfil 1: DefaultTransport  <br/> | TCP <br/> |
   |Perfil 1: saliente  <br/> | Desactivado <br/> |
   |Perfil 1: TlsVerify  <br/> | Activado <br/> |
   |Perfil 1: tipo  <br/> | Cisco <br/> |
   |Perfil 1: URI  <br/> | Asignado automáticamente en el registro CUCM <br/> |
   |Proxy 1: dirección  <br/> |El nombre de host de CUCM  <br/> |
   
Los VTC ahora están configurados para interoperación. Antes de que el servicio pueda comenzar, hay pasos finales para realizar en el lado CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurar dispositivos VTC en CUCM

1. Inicie sesión en CUCM y navegue a Cisco Unified CM Administration- \> Device- \> Teléfono- \> Find. 
    
2. Seleccione el dispositivo VTC que se va a configurar. Compruebe la siguiente configuración en la pantalla Teléfono configuración, corrificándose según sea necesario. Una vez que se haya cambiado o comprobado esta configuración, haga clic en **Guardar**.
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Información del dispositivo: Teléfono de botón  <br/> | Códec estándar de Cisco Telepresence C40 <br/> |
   |Información del dispositivo: perfil Teléfono común  <br/> | Perfil de Teléfono común estándar <br/> |
   |Información del dispositivo: espacio de búsqueda de llamadas  <br/> | CSS_SfBVideoInterop <br/> |
   |Información del dispositivo: espacio de búsqueda de llamadas de AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Información del dispositivo: lista de grupos de recursos multimedia  <br/> | MRGL_SfBVideoInterop <br/> |
   |Información específica del protocolo: perfil de seguridad de dispositivos  <br/> | Códec Cisco Telepresence C40 <br/> |
   |Información específica del protocolo: volver a enrir el espacio de búsqueda de llamadas  <br/> | CSS_SfBVideoInterop <br/> |
   |Información específica del protocolo: espacio de búsqueda de llamadas SUBSCRIBE  <br/> | CSS_SfBVideoInterop <br/> |
   |Información específica del protocolo -Perfil SIP  <br/> | Perfil SIP estándar para punto de conexión de telepresencia <br/> |
   
3. Una vez guardada la configuración de VTC, vuelva a navegar a la Teléfono configuración del dispositivo. En la parte superior de la pantalla del grupo Asociación, haga clic en la asociación para la interoperabilidad de vídeo. Esto muestra la pantalla Configuración de número de directorio. 
    
4. Compruebe la siguiente configuración, corrigiéndola según sea necesario: 
    
    Realice los cambios adecuados como se muestra en la información de número de directorio y el número de directorio Configuración.
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   | Información de número de directorio: partición de ruta <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Número de directorio Configuración: llamar al espacio de búsqueda  <br/> | CSS_SfBVideoInterop <br/> |
   |MlPP Alternate Party and Confidential Access Level Configuración - MLPP Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Línea 1 en el dispositivo: pantalla (identificador de autor de la llamada)  <br/> | Según lo deseado <br/> |
   |Línea 1 en el dispositivo: pantalla ASCII (identificador de autor de la llamada)  <br/> | Según lo deseado <br/> |
   
5. Cuando haya terminado, desplácese hasta la parte superior de la pantalla y presione **Guardar**. 
    
La configuración ya está completa para este dispositivo VTC. Deberá repetir este proceso para otros dispositivos VTC de su empresa.

