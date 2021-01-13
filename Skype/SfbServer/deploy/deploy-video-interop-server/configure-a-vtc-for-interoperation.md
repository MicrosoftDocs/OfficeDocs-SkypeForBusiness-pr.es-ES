---
title: Configurar una VTC para interoperación con Skype Empresarial Server
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
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802080"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurar una VTC para interoperación con Skype Empresarial Server
 
**Resumen:** Configure los dispositivos VTC para que funcionen con Skype Empresarial Server.
  
Deberá realizar los siguientes procedimientos de personalización de configuración para cada VTC que se conectará al servidor VIS de Skype Empresarial a través de un tronco SIP y una puerta de enlace de vídeo de Cisco Unified Communications Manager (CallManager o CUCM).
  
Las opciones que se describen aquí están pensadas solo como ejemplos de cómo CUCM se puede configurar para trabajar con un VIS. También se podrían usar otras opciones de configuración o usos de funcionalidades alternativas de CUCM para lograr el mismo resultado. No se recomienda la configuración óptima para un escenario determinado.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurar un VTC registrado con CUCM

1. Inicie sesión en el dispositivo Cisco VTC y vaya a Configuración- \> Configuración del sistema- \> Aprovisionamiento.
    
2. Compruebe la siguiente configuración, corrificándose según sea necesario: 
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Modo de aprovisionamiento  <br/> | CUCM <br/> |
   |ExternalManager Address  <br/> | FQDN de CUCM <br/> |
   | Dominio ExternalManager <br/> |Dominio de CUCM  <br/> |
   
3. Vaya a Configuración- \> Configuración del sistema- \> Red.
    
4. Compruebe la siguiente configuración, corrificándose según sea necesario: 
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Nombre de dominio DNS  <br/> | Nombre de dominio de CUCM <br/> |
   |Dirección del servidor DNS 1  <br/> | la dirección del servidor DNS que desee <br/> |
   
5. Vaya a Configuración- \> Configuración del sistema: \> Servicios de red. Asegúrese de que el modo H.323 está desactivado y que el modo SIP está activado. 
    
6. Estas opciones se establecen automáticamente cuando el extremo se registra con CUCM. Compruebe la siguiente configuración, corrificándose según sea necesario: 
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Modo H.323  <br/> | Desactivado <br/> |
   |Modo HTTP  <br/> | Activado <br/> |
   | Modo SIP <br/> | Activado <br/> |
   |Modo Telnet  <br/> | Activado <br/> |
   |WelcomeText  <br/> | Activado <br/> |
   |Modo XMLAPI  <br/> | Activado <br/> |
   
7. Vaya a Configuración- \> Configuración del sistema- \> SIP.
    
8. Compruebe la siguiente configuración, corrificándose según sea necesario: 
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Perfil 1: DefaultTransport  <br/> | TCP <br/> |
   |Perfil 1: saliente  <br/> | Desactivado <br/> |
   |Perfil 1: TlsVerify  <br/> | Activado <br/> |
   |Perfil 1: tipo  <br/> | Cisco <br/> |
   |Perfil 1: URI  <br/> | Asignado automáticamente en el registro de CUCM <br/> |
   |Proxy 1: dirección  <br/> |El nombre de host de CUCM  <br/> |
   
Los VTC ya están configurados para interoperación. Antes de que el servicio pueda comenzar, hay pasos finales para realizar en CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurar dispositivos VTC en CUCM

1. Inicie sesión en CUCM y vaya a Administración de Cisco Unified CM- \> \> Dispositivo- Teléfono- \> Buscar. 
    
2. Selecciona el dispositivo VTC que se va a configurar. Compruebe la siguiente configuración en la pantalla Configuración del teléfono, corrificándose según sea necesario. Una vez que se haya cambiado o comprobado esta configuración, haga clic en **Guardar.**
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Información del dispositivo: plantilla de botón Teléfono  <br/> | Standard Cisco Telepresence Codec C40 <br/> |
   |Información del dispositivo: perfil de teléfono común  <br/> | Perfil de teléfono común estándar <br/> |
   |Información del dispositivo: espacio de búsqueda de llamadas  <br/> | CSS_SfBVideoInterop <br/> |
   |Información del dispositivo: espacio de búsqueda de llamadas AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Información del dispositivo: lista de grupos de recursos multimedia  <br/> | MRGL_SfBVideoInterop <br/> |
   |Información específica del protocolo: perfil de seguridad del dispositivo  <br/> | Cisco Telepresence Codec C40 <br/> |
   |Información específica del protocolo: volver a enrear el espacio de búsqueda de llamadas  <br/> | CSS_SfBVideoInterop <br/> |
   |Información específica del protocolo: espacio de búsqueda de llamadas SUBSCRIBE  <br/> | CSS_SfBVideoInterop <br/> |
   |Información específica del protocolo :perfil SIP  <br/> | Perfil SIP estándar para el extremo de telepresencia <br/> |
   
3. Una vez guardada la configuración de VTC, vuelve a navegar a la pantalla Configuración del teléfono del dispositivo. En la parte superior de la pantalla del grupo Asociación, haga clic en la asociación para la interoperabilidad de vídeo. Se abre la pantalla Configuración de números de directorio. 
    
4. Compruebe la siguiente configuración, corrificándose según sea necesario: 
    
    Realice los cambios adecuados como se muestra en la información de número de directorio y la configuración de número de directorio.
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   | Información del número de directorio: partición de ruta <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Configuración del número de directorio: espacio de búsqueda de llamadas  <br/> | CSS_SfBVideoInterop <br/> |
   |Configuración de nivel de acceso confidencial y de parte alternativa de MLPP: espacio de búsqueda de llamadas de MLPP  <br/> | CSS_SfBVideoInterop <br/> |
   |Línea 1 en el dispositivo: pantalla (identificador de llamada)  <br/> | Según lo desee <br/> |
   |Línea 1 en el dispositivo - Pantalla ASCII (identificador de llamada)  <br/> | Según lo desee <br/> |
   
5. Cuando haya terminado, desplácese hasta la parte superior de la pantalla y presione **Guardar**. 
    
La configuración ya está completa para este dispositivo VTC. Deberás repetir este proceso para otros dispositivos VTC de tu empresa.

