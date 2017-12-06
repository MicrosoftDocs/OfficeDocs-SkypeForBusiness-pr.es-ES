---
title: "Servidores proxy para Skype Empresarial Online"
ms.author: tonysmit
author: tonysmit
ms.date: 11/6/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
description: "En este artículo se ofrecen algunas indicaciones sobre cómo usar un servidor proxy con Skype Empresarial."
---

# Servidores proxy para Skype Empresarial Online

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](7acaf2c2-35fa-490f-84cd-822e446e0fc7.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/7acaf2c2-35fa-490f-84cd-822e446e0fc7). 
  
En este artículo se ofrecen algunas indicaciones sobre cómo usar un servidor proxy con Skype Empresarial.
  
## Se recomienda no usar un servidor proxy

En lo que se refiere al tráfico de Skype Empresarial a través de servidores proxy, Microsoft recomienda omitirlos siempre que sea posible. Los servidores proxy no aportan una mayor seguridad a Skype Empresarial, ya que su tráfico ya está cifrado.
  
Y, sin embargo, tener un servidor proxy puede generar problemas; en concreto, se pueden crear problemas relacionados con el rendimiento en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos pueden crear una experiencia negativa en los escenarios de Skype Empresarial que impliquen audio y vídeo, en los que las secuencias en tiempo real son esenciales.
  
## Si necesita usar un servidor proxy

Algunas organizaciones no tienen ninguna opción para utilizar a un servidor proxy para Skype para el tráfico de la empresa. Si es el caso de, necesitan tener en cuenta los problemas mencionados.
  
Microsoft también recomienda:
  
- Usar una resolución DNS externa
    
- Usar UDP directo basado en el enrutamiento
    
- Permitir el tráfico UDP 
    
- Seguir las otras recomendaciones que aparecen en nuestras directrices de redes:
    
  - [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Optimizar la red para Skype Empresarial Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.
  
## Proveedores de servidores proxy con opciones de configuración o soporte de Skype Empresarial integrados

En esta sección encontrará información sobre proveedores de servidores proxy que proporcionan productos o servicios que han demostrado que funcionan correctamente con el tráfico de Skype Empresarial.
  
- Para organizaciones que usen **soluciones del servidor proxy Bluecoat**, se ha publicado un nuevo firmware que aborda varios problemas relacionados con:
    
  - Interceptación SSL
    
  - Comprobaciones OCSP/SRL
    
  - SIP sobre TLS
    
  - Soporte para TURN
    
    El soporte nativo de Bluecoat para Skype Empresarial se puede activar fácilmente, lo que permitirá identificar el tráfico relevante y gestionarlo correctamente. De este modo se garantiza una autenticación, señalización y un flujo de tráfico de medios óptimos para proporcionar una fantástica experiencia de usuario sin comprometer la seguridad.
    
    Consulte el siguiente vínculo si Bluecoat Proxy es parte de la topología de red
    
- https://support.Symantec.com/en_US/article.DOC9757.HTML
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

