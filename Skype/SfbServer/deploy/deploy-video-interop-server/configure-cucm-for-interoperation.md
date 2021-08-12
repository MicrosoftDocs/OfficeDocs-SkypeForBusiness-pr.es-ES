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
ms.openlocfilehash: c414e14feb29dc834ebcd6a62221e3ae5e6706e5ee5c265f155d6ea512a91423
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307761"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurar CUCM para interoperación con Skype Empresarial Server
 
**Resumen:** Configure CUCM para que funcione con Skype Empresarial Server.
  
> [!CAUTION]
> Esta funcionalidad se prueba con la versión 10.5 del Administrador de comunicaciones unificadas de Cisco (CallManager o CUCM) mediante la configuración de troncos solo a través de TCP. Compruebe que el entorno CUCM cumple estos criterios antes de continuar. 
  
Las configuraciones descritas aquí están pensadas solo como ejemplos de cómo CUCM puede configurarse para funcionar con un VIS. También se podrían usar otras configuraciones o usos de la funcionalidad cucm alternativa para lograr el mismo resultado. No se recomienda la configuración óptima para un escenario determinado.
  
Es necesario confirmar o cambiar una serie de configuraciones CUCM para interoperar con el VIS. Siga los procedimientos siguientes para evitar que falte la configuración necesaria.
  
### <a name="configure-the-cucm"></a>Configurar CUCM

1. Inicie sesión en CUCM y navegue a Cisco Unified CM Administration- \> Call Routing- \> Class of Control- \> Partition.
    
2. En la pantalla Configuración de partición, escriba el nombre y la descripción de la partición y haga clic **en Agregar nuevo**.
    
3. Navegue a Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Calling Search \> Space.
    
4. En la pantalla Configuración del espacio de búsqueda de llamadas, escriba el nombre del espacio de búsqueda de llamadas y, en Particiones seleccionadas, escriba el nombre de la partición que acaba de crear. Haga **clic en Guardar** cuando haya terminado.
    
5. Navegue a Cisco Unified CM Administration- \> System- \> Security- \> SIP Trunk Security Profile.
    
6. En la pantalla Configuración del perfil de seguridad del tronco SIP, establezca las opciones de información de perfil de seguridad de tronco SIP como se muestra y haga clic **en Agregar nuevo**.
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Nombre  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modo de seguridad de dispositivos  <br/> |No seguro  <br/> |
   |Tipo de transporte entrante  <br/> |TCP + UDP  <br/> |
   |Tipo de transporte saliente  <br/> |TCP  <br/> |
   |Puerto entrante  <br/> |5060  <br/> |
   
7. Navegue a Cisco Unified CM Administration- \> Device- \> Device Configuración- \> PERFIL SIP.
    
8. En la pantalla Configuración de perfil SIP, establezca las opciones de información de perfil SIP como se muestra. 
    
   |**Parámetro**|**Valor recomendado**|
   |:-----|:-----|
   |Nombre  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descripción  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. En la misma pantalla, desplácese hacia abajo hasta la sección Información de perfil de SDP. La **opción SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** está establecida de forma predeterminada en TIAS y AS. Cambie esta opción solo a TIAS. Si deja esta opción en su configuración predeterminada, Skype Empresarial Server comprenderá la información del modificador de ancho de banda en el mensaje SIP. TIAS significa Transport Independent Application Specific mientras que AS significa Application Specific. Estas son las opciones SIP especificadas en RFC3890.
    
10. En la misma pantalla, desplácese hacia abajo más adelante. En Configuración específica del tronco del  perfil SIP, selecciona Soporte de oferta anticipada para llamadas de voz y vídeo y establa en la opción Obligatorio **(insertar MTP** si es necesario). Esto permitirá a CUCM configurar una llamada SIP saliente con la oferta anticipada. Una nueva característica de CUCM 8.5 y posteriores es que admite la configuración de llamadas salientes con la oferta anticipada sin necesidad de punto de terminación de medios (MTP).
    
11. Compruebe que en la sección Ping opciones SIP, la casilla está activada junto a "Habilitar OPCIONES Ping para supervisar el estado de destino de los troncos con el tipo de servicio 'Ninguno (predeterminado)'".
    
12. Cuando haya terminado, haga clic en **Agregar nuevo**.
    
13. Navegue a Cisco Unified CM Administration- \> Device- \> Trunk. 
    
14. Establece el Protocolo de dispositivo en SIP y presiona **Siguiente**.
    
15. En Información del dispositivo, establece el nombre y la descripción del dispositivo (probablemente en algo como SfBVideoInterop_SIPTrunk) y establece la lista de grupos de recursos multimedia en un MRGL que contenga los recursos multimedia adecuados. 
    
16. Desplácese hacia abajo más adelante. El punto de terminación de medios (MTP) no es necesario para las videollamadas, si aún no está desactivada, desactíquela. Active la opción Ejecutar **en todos los nodos de CM unificados activos.** Tenga en cuenta que debe agregar todos los nodos CUCM a la Skype Empresarial Server configuración.
    
17. Desplácese hacia abajo más adelante. Establezca las opciones Llamadas entrantes y De Configuración como se muestra.
    
    |**Parámetro**|**Valor recomendado**|
    |:-----|:-----|
    |Llamar al espacio de búsqueda  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda de llamadas de AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS de transformación de partes conectadas  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Desplácese hacia abajo más adelante. En la sección Destino de información SIP de la configuración del tronco SIP, especifique el FQDN del grupo de VIS o la dirección IP de servidores VIS individuales del grupo (agregar varias entradas). En el puerto de destino, especifique el puerto en el que VIS escucha las conexiones de CUCM (el valor predeterminado es 6001). Especifique también el perfil de seguridad del tronco SIP y el perfil SIP que creó anteriormente, como se muestra.
    
    |**Parámetro**|**Valor recomendado**|
    |:-----|:-----|
    |Perfil de seguridad de tronco SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Volver a enrir el espacio de búsqueda de llamadas  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda de llamadas fuera del cuadro de diálogo  <br/> |CSS_SfBVideoInterop  <br/> |
    |Suscribirse al espacio de búsqueda de llamadas  <br/> |CSS_SfBVideoInterop  <br/> |
    |Perfil SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Dtmf Signaling (método)  <br/> |RFC 2833  <br/> |
   
19.  Desplácese hacia abajo más adelante. Establezca la información de grabación según corresponda para el sistema. Está bien dejarlo establecido en **None**. 
    
20. Cuando haya terminado, haga clic en **Agregar nuevo**.
    
21. Navegue a Cisco Unified CM Administration- \> Call Routing- \> Route/Hunt- \> Route pattern.
    
22. En la pantalla Configuración del patrón de ruta, escriba los parámetros de definición de patrón que se muestran a continuación. Desplácese hacia abajo hasta la sección Transformaciones de terceros llamadas y establezca la máscara como se muestra y, a continuación, haga clic **en Agregar nuevo** cuando haya terminado.
    
    |**Parámetro**|**Valor recomendado**|
    |:-----|:-----|
    |Patrón de ruta  <br/> |7779999  <br/> |
    |Partición de ruta  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descripción  <br/> |Partición para SfBVideoInterop  <br/> |
    |Lista de puertas de enlace/rutas  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Máscara de transformación de grupo denominada  <br/> |+14257779999  <br/> |
   
23. Navegue a Cisco Unified CM Administration- \> Call Routing- \> SIP Route Pattern.
    
24. En la pantalla Configuración del patrón de ruta SIP, establezca las opciones de definición de patrón como se muestra y haga clic **en Agregar nuevo**.
    
    |**Parámetro**|**Valor recomendado**|
    |:-----|:-----|
    | Uso de patrones <br/> |Enrutamiento de dominios  <br/> |
    |Patrón IPv4  <br/> |contoso.com (dejar en blanco si se usa IPv6)  <br/> |
    |Patrón IPv6  <br/> |contoso.com (dejar en blanco si se usa IPv4)  <br/> |
    |Descripción  <br/> |Patrón SIPRoute a mediarv  <br/> |
    |Partición de ruta  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Lista de troncos y rutas SIP  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Casilla Patrón de bloqueo  <br/> |leave unchecked  <br/> |
   
25. Si has cambiado las velocidades de bits de audio o vídeo de la configuración predeterminada, deberás devolverlas a los valores predeterminados. Para establecer la velocidad de bits de las llamadas de audio y vídeo, vaya a Cisco Unified CM Administration- \> System- \> Region Information- \> Region. Los valores predeterminados se muestran a continuación como referencia:
    
    |**Parámetro**|**Valor recomendado**|
    |:-----|:-----|
    |Región  <br/> |Predeterminado  <br/> |
    |Lista de preferencias de códec de audio  <br/> |Valor predeterminado del sistema  <br/> |
    |Velocidad máxima de bits de audio  <br/> |64 kbps (G.722, G.711)  <br/> |
    |Velocidad máxima de bits de sesión para videollamadas  <br/> |200000 kbps  <br/> |
    |Velocidad máxima de bits de sesión  <br/> |200000000 kbps  <br/> |
   
En este momento, la puerta de enlace de vídeo CUCM está configurada para funcionar con el VIS. La configuración correspondiente deberá realizarse en cada VTC que desee integrar.
> [!NOTE]
> Para mejorar la resistencia, es posible que desee configurar esta puerta de enlace CUCM para que funcione con un segundo servidor de interoperabilidad de vídeo o un grupo vis. Vea [Mecanismos de resistencia para](../../plan-your-deployment/video-interop-server.md#resiliency) obtener más información.
  
## <a name="see-also"></a>Consulte también

[Configurar un VTC para interoperación con Skype Empresarial Server](configure-a-vtc-for-interoperation.md)
