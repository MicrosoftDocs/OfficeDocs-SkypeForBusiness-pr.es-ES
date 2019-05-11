---
title: Configurar CUCM para la interoperación con Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Resumen: Configure CUCM para que funcione con Skype para Business Server.'
ms.openlocfilehash: 58896a635b389ca18506ca775ae4fb7715caf0ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894573"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurar CUCM para la interoperación con Skype para Business Server
 
**Resumen:** Configurar CUCM para que funcione con Skype para Business Server.
  
> [!CAUTION]
> Esta capacidad se haya probado con Cisco Unified Communications Manager (CallManager o CUCM) versión 10.5 mediante troncos de instalación sólo a través de TCP. Confirme que el entorno de CUCM cumple estos criterios antes de avanzar. 
  
La configuración que se describen aquí está diseñada sólo como ejemplos de cómo se puede configurar CUCM para funcionar con un VIS Se puede recurrir a otras configuraciones o a otros usos de funciones de CUCM distintas para lograr el mismo resultado. Este documento no tiene que tomarse como una recomendación de configuración óptima para un escenario en particular.
  
Es necesario confirmar o cambiar una serie de opciones de CUCM para la interoperación con el VIS. Realice los siguientes procedimientos para que no falte ninguna de las opciones necesarias.
  
### <a name="configure-the-cucm"></a>Configurar CUCM

1. Inicie sesión CUCM y vaya a Cisco Unified CM administración -\>enrutamiento de llamada -\>clase de Control -\>partición.
    
2. En la pantalla Configuración de partición, escriba el nombre de la partición y una descripción, y haga clic en **Agregar nuevo**.
    
3. Vaya a Cisco Unified CM administración -\>llamada enrutamiento -\>clase de Control -\>llamar al espacio de búsqueda.
    
4. En la pantalla Configuración de espacio de búsqueda de llamadas, escriba el nombre del espacio de búsqueda de llamadas y, en Particiones seleccionadas, escriba el nombre de la partición que acaba de crear. Haga clic en **Guardar** cuando termine.
    
5. Vaya a Cisco Unified CM administración -\>sistema -\>seguridad -\>perfil de seguridad de tronco SIP.
    
6. En la pantalla Configuración de perfil de seguridad de tronco SIP, establezca las opciones de información del perfil de seguridad de tronco SIP según se indica y haga clic en **Agregar nuevo**.
    
   |**Parámetro**|**Configuración recomendada**|
   |:-----|:-----|
   |Nombre  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modo de seguridad del dispositivo  <br/> |No protegido  <br/> |
   |Tipo de transporte entrante  <br/> |TCP + UDP  <br/> |
   |Tipo de transporte saliente  <br/> |TCP  <br/> |
   |Puerto entrante  <br/> |5060  <br/> |
   
7. Vaya a Cisco Unified CM administración -\>dispositivo -\>configuración de dispositivo -\>perfiles SIP.
    
8. En la pantalla Configuración del perfil SIP, establezca las opciones de información del perfil SIP según se indica. 
    
   |**Parámetro**|**Configuración recomendada**|
   |:-----|:-----|
   |Nombre  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descripción  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. En la misma pantalla, desplácese hacia abajo hasta la sección información de perfil de SDP. La opción **Modificador de ancho de banda de la sesión SDP para ofertas tempranas y nuevas invitaciones** está establecida de forma predeterminada en TIAS y AS. Cámbiela a solo TIAS. Si deja esta opción en su configuración predeterminada, Skype para Business Server no saben la información de modificador de ancho de banda en el mensaje SIP. TIAS son las siglas de Transport Independent Application Specific (aplicación específica de ancho de banda) y AS, las siglas de Application Specific (aplicación específica). Se trata de opciones de SIP especificadas en RFC3890.
    
10. En la misma pantalla, desplácese hacia abajo aún más. En la configuración específica del tronco del perfil de SIP, seleccione **Anticipado ofrecer compatibilidad con llamadas de voz y vídeo** y establézcalo en la opción **obligatorio (Insertar MTP si es necesario)** . Esto le permitirá CUCM configurar una llamada saliente de SIP con ofrecer anticipado. Una nueva característica en 8,5 CUCM y más allá de es que admite el establecimiento de llamadas salientes con ofrecer anticipado sin necesidad de punto de terminación de medios (MTP).
    
11. En la sección de ping de opciones de SIP, confirme que la casilla junto a "Habilitar ping de OPCIONES para supervisar el estado de destino de los troncos con el tipo de servicio 'Ninguno (predeterminado)'" está activada.
    
12. Cuando termine, haga clic en **Agregar nuevo**.
    
13. Vaya a Cisco Unified CM administración -\>dispositivo -\>tronco. 
    
14. Establezca el protocolo del dispositivo en SIP y presione **Siguiente**.
    
15. En la información del dispositivo, indique un nombre y una descripción para el dispositivo (probablemente, algo parecido a SfBVideoInterop_SIPTrunk) y establezca la lista del grupo de recursos del medio en una lista en la que figuren los recursos del medio adecuados. 
    
16. Siga bajando. El punto de terminación del medio (MTP) no es necesario en las llamadas de vídeo, así que desactive esta opción si aún no lo ha hecho. Active la opción **Ejecutar en todos los nodos de Unified CM**. Tenga en cuenta que debe agregar todos los nodos CUCM a la Skype para la configuración del servidor de negocio.
    
17. Siga bajando. Establezca las opciones de llamadas entrantes y la configuración de las partes conectadas según indicamos aquí.
    
    |**Parámetro**|**Configuración recomendada**|
    |:-----|:-----|
    |Espacio de búsqueda de llamadas  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda de llamadas AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS de transformación de parte conectada  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Desplácese hacia abajo un poco más. En la sección destino SIP de la información de la configuración del tronco SIP, especifique FQDN de la respecto del grupo de servidores o la dirección IP de los servidores individuales con respecto del grupo de servidores (agregar varias entradas). En el Puerto de destino, especifique el puerto de escucha del VIS para las conexiones de CUCM (el valor predeterminado es 6001). Especifique también el perfil de seguridad del tronco SIP y el perfil SIP que creó anteriormente, tal como se muestra.
    
    |**Parámetro**|**Configuración recomendada**|
    |:-----|:-----|
    |Perfil de seguridad del tronco SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Espacio de búsqueda de llamadas de reenrutamiento  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda de llamadas de referencia fuera de diálogo  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda de llamadas de suscripción  <br/> |CSS_SfBVideoInterop  <br/> |
    |Perfil SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Método de señalización DTMF  <br/> |RFC 2833  <br/> |
   
19.  Siga bajando. Establezca la información de grabación según sea adecuado para su sistema. Está bien dejar establecido en **Ninguno**. 
    
20. Cuando termine, haga clic en **Agregar nuevo**.
    
21. Navegue a Cisco Unified CM administración -\>enrutamiento de llamada -\>ruta/extensiones-\>modelo de ruta.
    
22. En la pantalla Configuración del patrón de ruta, indique los parámetros de definición del patrón aquí especificados. Baje a la sección de transformaciones de parte receptora de la llamada y defina la máscara como se muestra aquí. Cuando termine, haga clic en **Agregar nuevo**.
    
    |**Parámetro**|**Configuración recomendada**|
    |:-----|:-----|
    |Patrón de ruta  <br/> |7779999  <br/> |
    |Partición de ruta  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descripción  <br/> |Partición para SfBVideoInterop  <br/> |
    |Lista de puerta de enlace/ruta  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Máscara de transformación de parte receptora de la llamada  <br/> |+14257779999  <br/> |
   
23. Vaya a Cisco Unified CM administración -\>llamada enrutamiento -\>modelo de ruta de SIP.
    
24. En la pantalla Configuración de patrón de ruta SIP, establezca las opciones de definición del patrón como indicamos aquí y haga clic en **Agregar nuevo**.
    
    |**Parámetro**|**Configuración recomendada**|
    |:-----|:-----|
    | Uso del patrón <br/> |Enrutamiento de dominio  <br/> |
    |Patrón IPv4  <br/> |contoso.com (dejar vacío si se usa IPv6)  <br/> |
    |Patrón IPv6  <br/> |contoso.com (dejar vacío si se usa IPv4)  <br/> |
    |Descripción  <br/> |Patrón de SIPRoute a mediarv  <br/> |
    |Partición de ruta  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Lista de ruta/tronco SIP  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Casilla Bloquear patrón  <br/> |dejar sin activar  <br/> |
   
25. Si ha cambiado las velocidades de bits de audio o vídeo de la configuración predeterminada, deberá volver a los valores predeterminados. Para establecer la velocidad de bits para las llamadas de Audio y vídeo, navegue a Cisco Unified CM administración -\>sistema -\>información de región -\>región. A continuación se muestran los valores predeterminados a modo de referencia:
    
    |**Parámetro**|**Configuración recomendada**|
    |:-----|:-----|
    |Región  <br/> |Valor predeterminado  <br/> |
    |Lista de preferencias de códec de audio  <br/> |Valor predeterminado del sistema  <br/> |
    |Máxima velocidad de bits de audio  <br/> |64 kbps (G.722, G.711)  <br/> |
    |Máxima velocidad de bits de sesión para llamadas de vídeo  <br/> |200000 kbps  <br/> |
    |Máxima velocidad de bits de sesión  <br/> |2000000000 kbps  <br/> |
   
Llegado este punto, habrá configurado la puerta de enlace de vídeo de CUCM para que funcione con el VIS. Será necesario configurar lo que proceda en cada VTC que quiera integrar.
> [!NOTE]
> Para mejorar la resistencia, es posible que desee configurar esta puerta de enlace CUCM para que funcione con un segundo grupo de servidor de interoperabilidad de vídeo o con respecto. Mire [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para más información.
  
## <a name="see-also"></a>Vea también

[Configurar un VTC para la interoperación con Skype para Business Server](configure-a-vtc-for-interoperation.md)
