---
title: Plan para el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumen: lea este tema para obtener información sobre el Administrador de estadísticas para Skype Empresarial Server.'
ms.openlocfilehash: 166390fe0f034c907e21a3d3147b516d9f502954
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857407"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Plan para el administrador de estadísticas para Skype Empresarial Server

**Resumen:** Lea este tema para obtener información sobre el Administrador de estadísticas para Skype Empresarial Server.

 Statistics Manager for Skype Empresarial Server es una herramienta eficaz que le permite ver Skype Empresarial Server datos de rendimiento y estado en tiempo real. Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del Administrador de estadísticas.

Puede usar el Administrador de estadísticas para identificar problemas de rendimiento continuos, ver los resultados de un cambio planeado en su entorno, realizar un seguimiento de la resolución de interrupciones y mucho más. De forma rápida, el Administrador de estadísticas está configurado con umbrales del Indicador de mantenimiento clave (KHI) y se puede personalizar para adaptarse a las necesidades únicas de la implementación.

Puede implementar el Administrador de estadísticas en una implementación local en la que un solo servidor hospeda todos los componentes del Administrador de estadísticas del lado servidor. Para obtener más información acerca de la implementación del Administrador de estadísticas, vea [Deploy Statistics Manager for Skype Empresarial Server](deploy.md). Si ya tiene una implementación existente de Statistics Manager, pero aún no ha actualizado a la versión 2.0, consulte Novedades de la [versión 2.0](plan.md#BKMK_WhatsNew) y [Upgrade Statistics Manager for Skype Empresarial Server](upgrade.md).

En este tema se presentan las siguientes secciones:

- [Características y funciones](plan.md#BKMK_Features)

- [Novedades de la versión 2.0](plan.md#BKMK_WhatsNew)

- [Componentes](plan.md#BKMK_Components)

- [Implementación local](plan.md#BKMK_DeploymentOptions)

- [Requisitos](plan.md#BKMK_Requirements) 

- [Consideraciones de seguridad](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Características y funciones
<a name="BKMK_Features"> </a>

El Administrador de estadísticas le permite:

- Ver datos sin procesar para todos los servidores en tiempo real. (Los datos se muestra a una tasa muy alta y se envían al sitio web en menos de un segundo).

- Ver los datos agregados para un rol específico; por ejemplo, servidor front-end, servidor de mediación, servidor perimetral, entre otros.

- Explore en profundidad para ver los datos de sitios específicos, grupos de servidores específicos dentro del sitio y, a continuación, servidores específicos dentro del grupo.

- Cree gráficos personalizados para que los contadores elegidos se muestran de forma predeterminada.

- Zoom y desplazamiento panorámico en los ejes X e Y o solo en el eje X.

- Use intervalos de fechas o puntos en el tiempo para filtrar los datos.

- Ver el rendimiento del servidor en función de los indicadores de estado clave (KHIs) establecidos. Los KHIs representan una colección de contadores de rendimiento con un intervalo en buen estado definido.

- Ver métricas detalladas para cada contador.

- Compare los datos entre varias poblaciones o servidores.

- Ver informes de contadores latentes para identificar agentes que no notifican datos actuales al servicio de panel.

- Guarde una instancia determinada de datos del gráfico en un archivo.

- Ver KHIs en tiempo real, incluidas las actualizaciones. Si la vista de historial está habilitada, solo se muestran nuevos errores.

  - Ver todos los KHIs a la vez

  - Ver KHIs por servidor (vista horizontal)

  - Ver definiciones de KHI

## <a name="whats-new-in-release-20"></a>Novedades de la versión 2.0
<a name="BKMK_WhatsNew"> </a>

A continuación se describen las novedades de la versión 2.0. Si ya tiene una implementación de Statistics Manager y aún no ha actualizado, consulte [Upgrade Statistics Manager for Skype Empresarial Server](upgrade.md).

- Se han agregado vistas de escenarios para los escenarios de registro, mantenimiento de Fabric, Mantenimiento de Fabric y Conmutación por error del grupo.

- Se han agregado muchos contadores nuevos para SQL servidores, más Skype Empresarial contadores de uso, etc.

- Integración de nodos de monitor para el agente del administrador de estadísticas: si el agente está instalado en un nodo de monitor, se reportarán estadísticas de transacciones sintéticas como contadores al Administrador de estadísticas.

- Numerosas mejoras de confiabilidad y rendimiento.

Para comprobar la versión del sitio web del Administrador de estadísticas que está ejecutando:

- En el Explorador de archivos, abra (directorio predeterminado) C:\Archivos de programa\Skype Empresarial Server StatsMan WebSite\bin

- Haga clic con el botón StatsManHubWebSite.dll y vea sus propiedades

- La versión del producto se mostrará en los detalles de descripción.

## <a name="components"></a>Componentes
<a name="BKMK_Components"> </a>

El Administrador de estadísticas consta de los siguientes componentes:

- **Agente.** Un agente ligero que se ejecuta en cada servidor supervisado. El agente permite el sondeo de alta velocidad configurable de contadores de rendimiento con agregación local.

- **Escucha.** La API del lado servidor que recibe datos de todos los agentes y agrega datos entre poblaciones.

- **Concentrador.** Sirve como API de cliente para el sistema, se ejecuta en los servidores web y proporciona actualizaciones de datos en tiempo real a los clientes conectados a través del sitio web. (El concentrador se instala automáticamente como parte del msi del sitio web).

- **Sitio web.** Una interfaz de usuario que reúne todas las características disponibles en el sistema.

Además, el Administrador de estadísticas requiere **Redis**, un servidor de estructura de datos de código abierto para el almacenamiento en memoria caché. Para obtener más información acerca de la descarga de Redis, vea [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Implementación local
<a name="BKMK_DeploymentOptions"> </a>

En una implementación local, un solo servidor hospeda todos los componentes del administrador de estadísticas del lado servidor.

En el siguiente diagrama se muestra una implementación local, en la que el sitio web del Administrador de estadísticas, el sistema de almacenamiento en caché de Concentrador, Escucha y Redis se hospedan en un solo equipo. El Administrador de estadísticas supervisa tres Skype Empresarial, cada uno de los cuales tiene un único agente que transmite datos al agente de escucha. Los usuarios se conectan a un único sitio web para ver todos los datos agregados por el Administrador de estadísticas:

![Implementación local del Administrador de estadísticas.](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

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
- Descargar el [Skype Empresarial Server de estadísticas Real-Time (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Requisitos de red


|**Servidor de hospedaje**|**Agents**|**Escucha**|
|:-----|:-----|:-----|
|Red dúplex completa gigabit mínima.  <br/> |Puerto TCP saliente 8443 (número de puerto personalizable) para comunicarse con el agente de escucha.  <br/> |El puerto de escucha debe ser el mismo en todos los servidores.  <br/> |
|El puerto TCP entrante 80 o 443 se abre para hospedar el sitio web.  <br/> |||
|Puerto TCP entrante 8443 (número de puerto personalizable) para que los agentes se comuniquen con él.  <br/> |||

Durante la instalación, los puertos de firewall para el agente de escucha y el sitio web se crean automáticamente. Para los agentes, la instalación supone que las conexiones TCP salientes están permitidas de forma predeterminada.

### <a name="hardware-requirements"></a>Requisitos de hardware

En una implementación local, en la que un solo servidor hospeda todos los componentes del administrador de estadísticas del lado servidor, un servidor con 16 GB de RAM y 4 CPU debería admitir una media de 150 ejemplos por segundo. Para determinar cuántos contadores/agentes puede admitir, use el siguiente cálculo:

100 servidores 80 contadores 1 muestra por minuto de \* \* cada agente / 60 segundos = ~ 133 muestras por segundo.

## <a name="security-considerations"></a>Consideraciones acerca de la seguridad
<a name="BKMK_Security"> </a>

Todo el tráfico entre servidores está cifrado.

- El tráfico HTTPS cifrado se enviará a través del puerto 8443 (de forma predeterminada) desde el agente al servidor de escucha.

- El agente comprobará la huella digital SSL en el servidor para asegurarse de que el servidor de escucha es el destinatario esperado. Tenga en cuenta que el agente usa la comprobación de huella digital del certificado (en lugar de la verificación en cadena). No realizará la validación completa del certificado porque es posible usar certificados autofirmados.

- Una vez que el agente se haya satisfecho de que el agente de escucha es auténtico, el agente presentará una contraseña que luego será verificada por el agente de escucha.

- El agente comienza a transmitir datos de rendimiento a través de la conexión al agente de escucha.

## <a name="for-more-information"></a>Más información
<a name="BKMK_Security"> </a>

Para obtener más información, vea los artículos siguientes: 

- [Implementar el administrador de estadísticas para Skype Empresarial Server](deploy.md)

- [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md)

- [Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md)
