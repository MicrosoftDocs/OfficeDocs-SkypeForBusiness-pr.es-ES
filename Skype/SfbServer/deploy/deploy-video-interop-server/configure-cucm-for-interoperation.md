---
title: Configurar CUCM para interoperación con Skype Empresarial Server
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
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Resumen: configure CUCM para que funcione con Skype Empresarial Server.'
ms.openlocfilehash: 82fa48a185b22973d35bc19484e733e6436ba43e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837120"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurar CUCM para interoperación con Skype Empresarial Server
 
**Resumen:** Configure CUCM para que funcione con Skype Empresarial Server.
  
> [!CAUTION]
> Esta funcionalidad se prueba con Cisco Unified Communications Manager (CallManager, o CUCM) versión 10.5 mediante la configuración de troncos solo a través de TCP. Compruebe que el entorno cucm cumple estos criterios antes de continuar. 
  
Las opciones que se describen aquí están pensadas solo como ejemplos de cómo CUCM se puede configurar para trabajar con un VIS. También se podrían usar otras opciones de configuración o usos de funcionalidades alternativas de CUCM para lograr el mismo resultado. No se recomienda la configuración óptima para un escenario determinado.
  
Es necesario confirmar o cambiar una serie de configuraciones de CUCM para la interoperación con el VIS. Siga los procedimientos siguientes para evitar que falte la configuración necesaria.
  
### <a name="configure-the-cucm"></a>Configurar CUCM

1. Inicie sesión en CUCM y vaya a Administración de Cisco Unified CM- Enrutamiento de \> llamadas- \> Clase de control- \> Partición.
    
2. En la pantalla Configuración de partición, escriba el nombre y la descripción de la partición y haga clic **en Agregar nuevo**.
    
3. Vaya a Administración de Cisco Unified CM: \> Enrutamiento de llamadas- \> Clase de control- Espacio de búsqueda \> de llamadas.
    
4. En la pantalla Configuración del espacio de búsqueda de llamadas, escriba el nombre del espacio de búsqueda de llamadas y, en Particiones seleccionadas, escriba el nombre de la partición que acaba de crear. Haga **clic en Guardar** cuando haya terminado.
    
5. Vaya a Administración de Cisco Unified CM- \> Sistema- Seguridad- Perfil de seguridad \> del tronco \> SIP.
    
6. En la pantalla Configuración de perfil de seguridad de tronco SIP, establezca las opciones de información de perfil de seguridad de tronco SIP como se muestra y haga clic en **Agregar nuevo.**
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Nombre  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modo de seguridad de dispositivos  <br/> |No seguro  <br/> |
   |Tipo de transporte entrante  <br/> |TCP + UDP  <br/> |
   |Tipo de transporte saliente  <br/> |TCP  <br/> |
   |Puerto entrante  <br/> |5060  <br/> |
   
7. Vaya a Administración de Cisco Unified CM: \> Dispositivo- \> Configuración del dispositivo- \> Perfil SIP.
    
8. En la pantalla Configuración de perfil SIP, establezca las opciones de información de perfil SIP como se muestra. 
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Nombre  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descripción  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. En la misma pantalla, desplácese hacia abajo hasta la sección Información de perfil de SDP. El modificador de ancho de banda de nivel de sesión de **SDP** para la opción De oferta anticipada y volver a invitar está establecido de forma predeterminada en TIAS y AS. Cambie esta opción solo a TIAS. Si deja esta opción en su configuración predeterminada, Skype Empresarial Server no comprenderá la información del modificador de ancho de banda en el mensaje SIP. TIAS significa aplicación independiente de transporte específica mientras que AS significa aplicación específica. Estas son las opciones SIP especificadas en RFC3890.
    
10. En la misma pantalla, desplácese hacia abajo más adelante. En Configuración específica del tronco del  perfil SIP, seleccione Soporte de oferta anticipada para llamadas de voz y vídeo y estable la opción Obligatoria **(inserte MTP** si es necesario). Esto permitirá a CUCM configurar una llamada SIP saliente con la oferta anticipada. Una nueva característica de CUCM 8.5 y versiones posteriores es que admite la configuración de llamadas salientes con oferta anticipada sin necesidad de punto de terminación de medios (MTP).
    
11. Compruebe que, en la sección de ping de opciones SIP, la casilla está activada junto a "Habilitar ping de OPCIONES para supervisar el estado de destino de los troncos con tipo de servicio 'Ninguno (predeterminado)'".
    
12. Cuando haya terminado, haga clic en **Agregar nuevo.**
    
13. Vaya a Administración de Cisco Unified CM: \> tronco \> de dispositivo. 
    
14. Establezca el protocolo de dispositivo en SIP y presione **Siguiente**.
    
15. En Información del dispositivo, establece el nombre y la descripción del dispositivo (probablemente en algo parecido a SfBVideoInterop_SIPTrunk) y establece la lista de grupos de recursos multimedia en un MRGL que contenga los recursos multimedia adecuados. 
    
16. Desplácese hacia abajo más adelante. El punto de terminación de medios (MTP) no es necesario para las videollamadas, si aún no está desactivada, desactíbala. Active la opción Ejecutar **en todos los nodos de CM unificados activos.** Tenga en cuenta que debe agregar todos los nodos cucm a la configuración de Skype Empresarial Server.
    
17. Desplácese hacia abajo más adelante. Establezca las opciones Llamadas entrantes y Configuración de terceros conectados como se muestra.
    
    |**Parámetro**|**Valor recomendado**|
    |:-----|:-----|
    |Espacio de búsqueda de llamadas  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda de llamadas de AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS de transformación de parte conectada  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Desplácese hacia abajo más adelante. En la sección Destino de información SIP de la configuración del tronco SIP, especifique el FQDN del grupo de servidores VIS o la dirección IP de los servidores VIS individuales del grupo de servidores (agregando varias entradas). En el puerto de destino, especifique el puerto en el que el VIS escucha las conexiones de CUCM (el valor predeterminado es 6001). Especifique también el perfil de seguridad del tronco SIP y el perfil SIP que creó anteriormente, como se muestra.
    
    |**Parámetro**|**Valor recomendado**|
    |:-----|:-----|
    |Perfil de seguridad de tronco SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Volver a enrear el espacio de búsqueda de llamadas  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda de llamadas sin cuadro de diálogo  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda para suscribirse a llamadas  <br/> |CSS_SfBVideoInterop  <br/> |
    |Perfil SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DtMF Signaling (método)  <br/> |RFC 2833  <br/> |
   
19.  Desplácese hacia abajo más adelante. Establezca la información de grabación según corresponda al sistema. Está bien dejarla establecida en **Ninguno**. 
    
20. Cuando haya terminado, haga clic en **Agregar nuevo.**
    
21. Vaya a Administración de Cisco Unified CM: \> Enrutamiento de llamadas- \> Ruta/Búsqueda- \> Patrón de ruta.
    
22. En la pantalla Configuración del patrón de ruta, escribe los parámetros de definición de patrón que se muestran a continuación. Desplácese hacia abajo hasta la sección Transformaciones de parte llamada y establezca la máscara como se muestra y, a continuación, haga clic en **Agregar nuevo** cuando haya terminado.
    
    |**Parámetro**|**Valor recomendado**|
    |:-----|:-----|
    |Patrón de ruta  <br/> |7779999  <br/> |
    |Partición de ruta  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descripción  <br/> |Partición para SfBVideoInterop  <br/> |
    |Lista de puertas de enlace/rutas  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Máscara de transformación de parte llamada  <br/> |+14257779999  <br/> |
   
23. Vaya a Administración de Cisco Unified CM: \> Enrutamiento de llamadas- Patrón \> de ruta SIP.
    
24. En la pantalla Configuración del patrón de ruta SIP, establezca las opciones de definición de patrón como se muestra y haga clic en **Agregar nuevo.**
    
    |**Parámetro**|**Valor recomendado**|
    |:-----|:-----|
    | Uso de patrones <br/> |Enrutamiento de dominios  <br/> |
    |Patrón IPv4  <br/> |contoso.com (dejar en blanco si se usa IPv6)  <br/> |
    |Patrón IPv6  <br/> |contoso.com (dejar en blanco si se usa IPv4)  <br/> |
    |Descripción  <br/> |Patrón SIPRoute a mediarv  <br/> |
    |Partición de ruta  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Lista de troncos y rutas SIP  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Casilla patrón de bloqueo  <br/> |leave unchecked  <br/> |
   
25. Si ha cambiado las velocidades de bits de audio o vídeo de la configuración predeterminada, deberá devolverlas a los valores predeterminados. Para establecer la velocidad de bits de las llamadas de audio y vídeo, vaya a Administración de Cisco Unified \> CM- Sistema- \> Información de región- \> Región. Los valores predeterminados se muestran a continuación como referencia:
    
    |**Parámetro**|**Valor recomendado**|
    |:-----|:-----|
    |Región  <br/> |Predeterminado  <br/> |
    |Lista de preferencias de códecs de audio  <br/> |Valor predeterminado del sistema  <br/> |
    |Velocidad máxima de bits de audio  <br/> |64 kbps (G.722, G.711)  <br/> |
    |Velocidad de bits máxima de sesión para videollamadas  <br/> |200000 kbps  <br/> |
    |Velocidad de bits máxima de sesión  <br/> |2000000000 kbps  <br/> |
   
En este punto, la puerta de enlace de vídeo de CUCM está configurada para funcionar con el VIS. La configuración correspondiente deberá realizarse en cada VTC que quieras integrar.
> [!NOTE]
> Para mejorar la resistencia, es posible que desee configurar esta puerta de enlace CUCM para que funcione con un segundo servidor de interoperabilidad de vídeo o un grupo vis. Vea [los mecanismos de resistencia para](../../plan-your-deployment/video-interop-server.md#resiliency) obtener más información.
  
## <a name="see-also"></a>Vea también

[Configurar una VTC para interoperación con Skype Empresarial Server](configure-a-vtc-for-interoperation.md)
