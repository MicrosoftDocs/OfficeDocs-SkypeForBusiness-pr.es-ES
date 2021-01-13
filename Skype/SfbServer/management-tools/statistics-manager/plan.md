---
title: Plan para el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumen: lea este tema para obtener información sobre el Administrador de estadísticas de Skype Empresarial Server.'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821830"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Plan para el administrador de estadísticas para Skype Empresarial Server

**Resumen:** Lea este tema para obtener información sobre el Administrador de estadísticas de Skype Empresarial Server.

 El Administrador de estadísticas de Skype Empresarial Server es una herramienta eficaz que le permite ver datos de rendimiento y estado de Skype Empresarial Server en tiempo real. Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del Administrador de estadísticas.

Puede usar el Administrador de estadísticas para identificar problemas de rendimiento continuos, ver los resultados de un cambio planeado en su entorno, realizar un seguimiento de la resolución de interrupciones y mucho más. De forma rápida, el Administrador de estadísticas está configurado con umbrales de indicador de estado clave (KHI) y se puede personalizar para adaptarse a las necesidades únicas de la implementación.

Puede implementar el Administrador de estadísticas en una implementación local en la que un único servidor hospeda todos los componentes del Administrador de estadísticas del lado servidor. Para obtener más información acerca de la implementación del Administrador de estadísticas, consulte Implementar el Administrador de [estadísticas para Skype Empresarial Server.](deploy.md) If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).

En este tema se presentan las siguientes secciones:

- [Características y capacidades](plan.md#BKMK_Features)

- [Novedades de la versión 2.0](plan.md#BKMK_WhatsNew)

- [Componentes](plan.md#BKMK_Components)

- [Implementación local](plan.md#BKMK_DeploymentOptions)

- [Requisitos](plan.md#BKMK_Requirements) 

- [Consideraciones de seguridad](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Características y capacidades
<a name="BKMK_Features"> </a>

El Administrador de estadísticas le permite:

- Ver datos sin procesar para todos los servidores en tiempo real. (Los datos se muestra a una velocidad muy alta y se envían al sitio web en menos de un segundo).

- Ver los datos agregados para un rol específico; por ejemplo, servidor front-end, servidor de mediación, servidor perimetral, entre otros.

- Explore en profundidad para ver datos de sitios específicos, grupos específicos dentro del sitio y, a continuación, servidores específicos dentro del grupo.

- Cree gráficos personalizados para que los contadores seleccionados se muestran de forma predeterminada.

- Zoom y movimiento panorámico en los ejes x e y, o solo en el eje X.

- Use intervalos de fechas o puntos de tiempo para filtrar datos.

- Ver el rendimiento del servidor en función de los indicadores clave de estado (KHIs) establecidos. Los KHIs representan una colección de contadores de rendimiento con un rango en buen estado definido.

- Ver métricas detalladas para cada contador.

- Compare los datos en varias poblaciones o servidores.

- Ver informes de contadores latentes para identificar agentes que no notifican datos actuales al servicio de panel.

- Guarde una instancia determinada de los datos del gráfico en un archivo.

- Ver los KHIs en tiempo real, incluidas las actualizaciones. Si la vista de historial está habilitada, solo se muestran nuevos errores.

  - Ver todos los KHIs a la vez

  - Ver LOS KHIs por servidor (vista horizontal)

  - Ver definiciones de KHI

## <a name="whats-new-in-release-20"></a>Novedades de la versión 2.0
<a name="BKMK_WhatsNew"> </a>

A continuación se describen las novedades de la versión 2.0. If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).

- Se han agregado vistas de escenario para los escenarios de medios perimetrales, mantenimiento de Fabric, conmutación por error de grupo y registro.

- Se han agregado muchos contadores nuevos para SQL servidores, más contadores de uso de Skype Empresarial, etc.

- Integración del nodo de monitor para el agente del Administrador de estadísticas: si el agente está instalado en un nodo de monitor, se mostrarán las estadísticas de transacciones sintéticas como contadores al Administrador de estadísticas.

- Numerosas mejoras de confiabilidad y rendimiento.

Para comprobar la versión del sitio web del Administrador de estadísticas que está ejecutando:

- En el Explorador de archivos, abra (directorio predeterminado) C:\Archivos de programa\Skype Empresarial Server StatsMan WebSite\bin

- Haga clic con el botón StatsManHubWebSite.dll y vea sus propiedades

- La versión del producto se mostrará en los detalles de descripción.

## <a name="components"></a>Componentes
<a name="BKMK_Components"> </a>

El Administrador de estadísticas consta de los siguientes componentes:

- **Agente.** Un agente ligero que se ejecuta en cada servidor supervisado. El agente permite sondeos de alta velocidad configurables de contadores de rendimiento con agregación local.

- **Escucha.** La API del lado servidor que recibe datos de todos los agentes y agrega datos entre las distintas poblaciones.

- **Hub.** Actúa como la API de cliente para el sistema, se ejecuta en los servidores web y proporciona actualizaciones de datos en tiempo real a los clientes conectados a través del sitio web. (El concentrador se instala automáticamente como parte del msi del sitio web).

- **Sitio web.** Una interfaz de usuario que reúne todas las características disponibles en el sistema.

Además, el Administrador de estadísticas requiere **Redis,** un servidor de estructura de datos de código abierto para el almacenamiento en memoria caché. Para obtener más información acerca de cómo descargar Redis, vea [Implementar el Administrador de estadísticas.](deploy.md#BKMK_Deploy)

## <a name="on-premises-deployment"></a>Implementación local
<a name="BKMK_DeploymentOptions"> </a>

En una implementación local, un único servidor hospeda todos los componentes del Administrador de estadísticas del lado servidor.

El siguiente diagrama muestra una implementación local, en la que el sitio web del Administrador de estadísticas, el sistema de almacenamiento en caché de Concentradores, Escucha y Redis se hospedan en un único equipo. El Administrador de estadísticas supervisa tres servidores de Skype Empresarial, cada uno de los cuales tiene un único agente que transmite datos a la escucha. Los usuarios se conectan a un único sitio web para ver todos los datos agregados por el Administrador de estadísticas:

![Implementación local del Administrador de estadísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Requisitos
<a name="BKMK_Requirements"> </a>

Deberá tener en cuenta los siguientes requisitos de software, redes y hardware antes de implementar el Administrador de estadísticas.

### <a name="software-requirements"></a>Requisitos de software

- Windows Server 2016 y 2019

- IIS (instalado automáticamente)

- Redis

- Servicios del Administrador de estadísticas (instalados automáticamente)

- PSExec: necesario para realizar la implementación de agentes remotos

- .NET 4.5 (incluido con 2012 R2): necesario para agentes y componentes del lado servidor
- Descargar Skype [Empresarial Server, administrador de Real-Time de estadísticas (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Requisitos de red


|**Servidor de hospedaje**|**Agents**|**Listener**|
|:-----|:-----|:-----|
|Red de dúplex completo de gigabit mínimo.  <br/> |Puerto TCP saliente 8443 (número de puerto personalizable) para comunicarse con el agente de escucha.  <br/> |El puerto de escucha debe ser el mismo en todos los servidores.  <br/> |
|El puerto TCP de entrada 80 o 443 se abre para hospedar el sitio web.  <br/> |||
|Puerto TCP de entrada 8443 (número de puerto personalizable) para que los agentes se comuniquen con él.  <br/> |||

Durante la instalación, los puertos de firewall para la escucha y el sitio web se crean automáticamente. Para los agentes, la instalación supone que las conexiones TCP salientes están permitidas de forma predeterminada.

### <a name="hardware-requirements"></a>Requisitos de hardware

En una implementación local, en la que un único servidor hospeda todos los componentes del Administrador de estadísticas del lado servidor, un servidor con 16 GB de RAM y 4 CPU debería ser capaz de admitir una media de 150 muestras por segundo. Para determinar cuántos contadores/agentes puede admitir, use el siguiente cálculo:

100 servidores 80 contadores 1 muestra por minuto de cada agente \* / 60 segundos = ~ \* 133 muestras por segundo.

## <a name="security-considerations"></a>Consideraciones acerca de la seguridad
<a name="BKMK_Security"> </a>

Todo el tráfico entre servidores está cifrado.

- El tráfico HTTPS cifrado se enviará a través del puerto 8443 (de forma predeterminada) desde el agente al servidor de escucha.

- El agente comprobará la huella digital SSL en el servidor para asegurarse de que el servidor de escucha es el destinatario esperado. Tenga en cuenta que el agente usa la comprobación de huella digital del certificado (en lugar de la verificación en cadena). No realizará la validación completa del certificado porque es posible usar certificados autofirmados.

- Una vez que el agente está satisfecho con que la escucha es autenticada, el agente presentará una contraseña que, a continuación, la agente de escucha comprobará.

- El agente comienza a transmitir datos de rendimiento a través de la conexión a la escucha.

## <a name="for-more-information"></a>Más información
<a name="BKMK_Security"> </a>

Para obtener más información, vea los artículos siguientes: 

- [Implementar el administrador de estadísticas para Skype Empresarial Server](deploy.md)

- [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md)

- [Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md)
