---
title: Configurar CUCM de interoperación con Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Resumen: Configurar CUCM para trabajar con Skype para Business Server 2015.'
ms.openlocfilehash: f05b55b875cb344da369f5fd74f16a73faf43907
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server-2015"></a>Configurar CUCM de interoperación con Skype Empresarial Server 2015
 
**Resumen:** Configurar CUCM para trabajar con Skype para Business Server 2015.
  
> [!CAUTION]
> Esta capacidad se comprueba con CUCM versión 10.5 usando únicamente la configuración de troncos sobre TCP. Confirme que el entorno de CUCM cumple estos criterios antes de avanzar. 
  
La configuración descrita aquí está diseñada sólo como ejemplos de cómo se puede configurar CUCM para funcionar con un VIS. Se puede recurrir a otras configuraciones o a otros usos de funciones de CUCM distintas para lograr el mismo resultado. Este documento no tiene que tomarse como una recomendación de configuración óptima para un escenario en particular.
  
Es necesario confirmar o cambiar una serie de opciones de CUCM para la interoperación con el VIS. Realice los siguientes procedimientos para que no falte ninguna de las opciones necesarias.
  
### <a name="configure-the-cucm"></a>Configurar CUCM

1. Inicie sesión en CUCM y vaya a Cisco Unified CM Administration -\>llamada enrutamiento -\>clase de Control -\>partición.
    
2. En la pantalla Configuración de partición, escriba el nombre de la partición y una descripción, y haga clic en **Agregar nuevo**.
    
3. Vaya a Cisco Unified CM Administration -\>llamar al enrutamiento -\>la clase de Control -\>llamada espacio de búsqueda.
    
4. En la pantalla Configuración de espacio de búsqueda de llamadas, escriba el nombre del espacio de búsqueda de llamadas y, en Particiones seleccionadas, escriba el nombre de la partición que acaba de crear. Haga clic en **Guardar** cuando termine.
    
5. Desplácese a Cisco Unified CM Administration -\>sistema -\>Security -\>perfil de seguridad de troncal SIP.
    
6. En la pantalla Configuración de perfil de seguridad de tronco SIP, establezca las opciones de información del perfil de seguridad de tronco SIP según se indica y haga clic en **Agregar nuevo**.
    
   |**Parámetro**|**Configuración recomendada**|
   |:-----|:-----|
   |Nombre  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modo de seguridad del dispositivo  <br/> |No protegido  <br/> |
   |Tipo de transporte entrante  <br/> |TCP + UDP  <br/> |
   |Tipo de transporte saliente  <br/> |TCP  <br/> |
   |Puerto entrante  <br/> |5060  <br/> |
   
7. Desplácese a Cisco Unified CM Administration -\>dispositivo -\>configuración de dispositivo -\>perfil SIP.
    
8. En la pantalla Configuración del perfil SIP, establezca las opciones de información del perfil SIP según se indica. 
    
   |**Parámetro**|**Configuración recomendada**|
   |:-----|:-----|
   |Nombre  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descripción  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. En la misma pantalla, desplácese hacia abajo hasta la sección información de perfil de SDP. La opción **Modificador de ancho de banda de la sesión SDP para ofertas tempranas y nuevas invitaciones** está establecida de forma predeterminada en TIAS y AS. Cámbiela a solo TIAS. Si deja esta opción en su configuración predeterminada, Skype para Business Server no comprenderá la información del modificador de ancho de banda en el mensaje SIP. TIAS son las siglas de Transport Independent Application Specific (aplicación específica de ancho de banda) y AS, las siglas de Application Specific (aplicación específica). Se trata de opciones de SIP especificadas en RFC3890.
    
10. En la misma pantalla, desplácese hacia abajo aún más. En configuración específica del tronco del perfil de SIP, seleccione ** temprano ofrecen soporte para llamadas de voz y vídeo ** y establezca la opción **obligatorio (Insertar MTP si es necesario)** . Esto le permitirá CUCM configurar una llamada SIP saliente con oferta temprana. Una nueva característica en CUCM 8.5 y versiones posteriores es que admite configuración de llamada saliente con oferta temprana sin necesidad de punto de terminación de multimedia (MTP).
    
11. En la sección de ping de opciones de SIP, confirme que la casilla junto a "Habilitar ping de OPCIONES para supervisar el estado de destino de los troncos con el tipo de servicio 'Ninguno (predeterminado)'" está activada.
    
12. Cuando termine, haga clic en **Agregar nuevo**.
    
13. Desplácese a Cisco Unified CM Administration -\>dispositivo -\>tronco. 
    
14. Establezca el protocolo del dispositivo en SIP y presione **Siguiente**.
    
15. En la información del dispositivo, indique un nombre y una descripción para el dispositivo (probablemente, algo parecido a SfBVideoInterop_SIPTrunk) y establezca la lista del grupo de recursos del medio en una lista en la que figuren los recursos del medio adecuados. 
    
16. Siga bajando. El punto de terminación del medio (MTP) no es necesario en las llamadas de vídeo, así que desactive esta opción si aún no lo ha hecho. Active la opción **Ejecutar en todos los nodos de Unified CM**. Tenga en cuenta que debe agregar todos los nodos CUCM para el Skype para la configuración del servidor de empresa.
    
17. Siga bajando. Establezca las opciones de llamadas entrantes y la configuración de las partes conectadas según indicamos aquí.
    
    |**Parámetro**|**Configuración recomendada**|
    |:-----|:-----|
    |Espacio de búsqueda de llamadas  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda de llamadas AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS de transformación de parte conectada  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Desplácese hacia abajo un poco más. En la sección destino SIP de la información de la configuración de troncal SIP, especificar FQDN del grupo VIS o la dirección IP de los servidores individuales de VIS en el grupo (agregar varias entradas). En el Puerto de destino, especifique el puerto de escucha del VIS para las conexiones de CUCM (el valor predeterminado es 6001). Especifique también el perfil de seguridad del tronco SIP y el perfil SIP que creó anteriormente, tal como se muestra.
    
    |**Parámetro**|**Configuración recomendada**|
    |:-----|:-----|
    |Perfil de seguridad del tronco SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Espacio de búsqueda de llamadas de reenrutamiento  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda de llamadas de referencia fuera de diálogo  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espacio de búsqueda de llamadas de suscripción  <br/> |CSS_SfBVideoInterop  <br/> |
    |Perfil SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Método de señalización DTMF  <br/> |RFC 2833  <br/> |
   
19.  Siga bajando. Establezca la información de grabación según sea adecuado para su sistema. Está bien dejarlo establecido en **Ninguno**. 
    
20. Cuando termine, haga clic en **Agregar nuevo**.
    
21. Desplácese a Cisco Unified CM Administration -\>llamada enrutamiento -\>ruta/Hunt-\>modelo de ruta.
    
22. En la pantalla Configuración del patrón de ruta, indique los parámetros de definición del patrón aquí especificados. Baje a la sección de transformaciones de parte receptora de la llamada y defina la máscara como se muestra aquí. Cuando termine, haga clic en **Agregar nuevo**.
    
    |**Parámetro**|**Configuración recomendada**|
    |:-----|:-----|
    |Patrón de ruta  <br/> |7779999  <br/> |
    |Partición de ruta  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descripción  <br/> |Partición para SfBVideoInterop  <br/> |
    |Lista de puerta de enlace/ruta  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Máscara de transformación de parte receptora de la llamada  <br/> |+14257779999  <br/> |
   
23. Desplácese a Cisco Unified CM Administration -\>llamar al enrutamiento -\>patrón de enrutamiento SIP.
    
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
   
25. Si ha cambiado las velocidades de bits de audio o vídeo de la configuración predeterminada, deberá volver a los valores predeterminados. Para establecer la velocidad de bits para llamadas de Audio y vídeo, vaya a Cisco Unified CM Administration -\>sistema -\>información región -\>región. A continuación se muestran los valores predeterminados a modo de referencia:
    
    |**Parámetro**|**Configuración recomendada**|
    |:-----|:-----|
    |Región  <br/> |Valor predeterminado  <br/> |
    |Lista de preferencias de códec de audio  <br/> |Valor predeterminado del sistema  <br/> |
    |Máxima velocidad de bits de audio  <br/> |64 kbps (G.722, G.711)  <br/> |
    |Máxima velocidad de bits de sesión para llamadas de vídeo  <br/> |200000 kbps  <br/> |
    |Máxima velocidad de bits de sesión  <br/> |2000000000 kbps  <br/> |
   
Llegado este punto, habrá configurado la puerta de enlace de vídeo de CUCM para que funcione con el VIS. Será necesario configurar lo que proceda en cada VTC que quiera integrar.
> [!NOTE]
> Para mejorar la resiliencia, es aconsejable configurar esta puerta de enlace CUCM para que funcione con un segundo servidor de interoperabilidad de vídeo o VIS piscina. Mire [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para más información.
  
## <a name="see-also"></a>Vea también

#### 

[Configurar una VTC para la interoperación con Skype para Business Server 2015](configure-a-vtc-for-interoperation.md)

