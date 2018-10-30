---
title: "Lync Server 2013: Tecnologías de virtualización admitidas y limitaciones comunes"
TOCTitle: Tecnologías de virtualización admitidas y limitaciones comunes
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48275578
ms.date: 02/06/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tecnologías de virtualización admitidas y limitaciones comunes en Lync Server 2013

 

_**Última modificación del tema:** 2017-02-06_

El complemento VDI de Lync permite realizar llamadas con audio y video con tecnologías de virtualización compatibles. Esto amplía la funcionalidad descrita para Microsoft Lync Server 2010 en las notas del producto [Virtualización del cliente en Microsoft Lync 2010](http://go.microsoft.com/fwlink/?linkid=330447). Conforme a las normativas estándar para teléfonos, también se incluye soporte para E911. En las secciones que siguen se describen las tecnologías de virtualización que son compatibles con el complemento VDI de Lync y las limitaciones comunes de las funciones.

## Soporte de tecnologías de virtualización

El complemento VDI de Lync admite comunicación remota completa de escritorio en el entorno de escritorio virtual personal, pero no en el entorno de sesión de escritorio remoto. Estos entornos pueden describirse así:

  - **Admitidos: escritorios virtuales personalizados o infraestructura de escritorio virtual (VDI).** En este entorno, cada usuario inicia sesión en un escritorio virtual personalizable y puede guardar archivos en el escritorio, que se conservan entre sesiones. Los servicios de Escritorio remoto de Microsoft, VMware Horizon View y Citrix XenDesktop son implementaciones cuyo uso ya se ha probado con Lync. Para obtener información sobre entornos VDI específicos de proveedor y hardware de clientes que hayan sido probados por Microsoft, consulte [Infraestructura apta para Microsoft Lync](http://go.microsoft.com/fwlink/?linkid=313435).

  - **No admitidos: sesiones de escritorio remoto.**   En este entorno, cada usuario inicia sesión en una sesión de escritorio virtual genérica que no puede personalizarse. Algunos ejemplos de implementaciones son las sesiones de escritorio remoto de Microsoft (RDSH) y Citrix XenApp combinadas con Citrix Receiver.

El complemento VDI de Lync no admite otras tecnologías de virtualización, como la virtualización de aplicaciones, que permite el uso de una aplicación sin necesidad de instalar la aplicación completa de forma local. Algunos ejemplos de implementaciones son Citrix XenApp y Microsoft Application Virtualization (App-V). El streaming de aplicaciones, la comunicación remota de aplicaciones y los modos mixtos de virtualización (por ejemplo, la comunicación remota de aplicaciones en la comunicación remota de escritorio completa) no se admiten.

Para permitir extensibilidad, el complemento VDI de Lync se diseñó para utilizar API independientes de la plataforma, denominadas canales virtuales dinámicos (DVC). En el caso de entornos que Lync no admite de forma explícita, consulte las instrucciones de compatibilidad del proveedor de la solución de VDI.

## Limitaciones comunes de la funciones

A continuación se indican algunas limitaciones comunes que surgen cuando se utiliza Lync 2013 en un entorno de VDI:

  - La compatibilidad es limitada para las características de delegación de llamada y de anonimato de agente (Agent Anonymization) de Grupo de respuesta.

  - No se admiten estas características:
    
      - Las páginas de ajuste del dispositivo de audio y de vídeo integrados.
    
      - El vídeo de múltiples vistas.
    
      - La grabación de las conversaciones.
    
      - La unión a reuniones de forma anónima (es decir, unirse a reuniones de Lync hospedadas por una organización sin relaciones de federación con la suya).
    
      - El uso del complemento VDI de Lync al mismo tiempo que un dispositivo de Lync Phone Edition.
    
      - La continuación de llamadas en caso de una interrupción de la red.
    
      - Las características de tonos de llamada personalizados y de música en espera.

  - El complemento VDI de Lync no se admite en un entorno de Office 365.

