---
title: Planear el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumen: Lea este tema para obtener información sobre statistic Manager para Skype empresarial Server.'
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816239"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planear el administrador de estadísticas para Skype Empresarial Server

**Resumen:** Lea este tema para obtener información sobre statistic Manager para Skype empresarial Server.

 El administrador de estadísticas de Skype Empresarial Server es una eficaz herramienta que le permite ver los datos de mantenimiento y rendimiento de Skype Empresarial Server en tiempo real. Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del administrador de estadísticas.

Puede usar Statistics Manager para identificar problemas de rendimiento continuo, ver los resultados de un cambio planificado en su entorno, realizar un seguimiento de la resolución de las interrupciones y mucho más. El administrador de estadísticas está configurado con los umbrales del indicador de mantenimiento de clave (KHI), y se puede personalizar según las necesidades exclusivas de su implementación.

Puede implementar el administrador de estadísticas en una implementación local en la que un solo servidor hospede todos los componentes del administrador de estadísticas del servidor. Para obtener más información sobre cómo implementar statistic Manager, consulte [implementar el administrador de estadísticas para Skype empresarial Server](deploy.md). Si ya tiene una implementación existente de Statistics Manager, pero aún no ha actualizado a la versión 2,0, consulte [novedades de la versión 2,0](plan.md#BKMK_WhatsNew) y al [Administrador de estadísticas de actualización para Skype empresarial Server](upgrade.md).

Este tema incluye las secciones siguientes:

- [Características y capacidades](plan.md#BKMK_Features)

- [Novedades de la versión 2,0](plan.md#BKMK_WhatsNew)

- [Componentes](plan.md#BKMK_Components)

- [Implementación local](plan.md#BKMK_DeploymentOptions)

- [Requisitos](plan.md#BKMK_Requirements) 

- [Consideraciones de seguridad](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Características y capacidades
<a name="BKMK_Features"> </a>

Statistic Manager le permite:

- Ver datos sin procesar de todos los servidores en tiempo real. (Los datos se muestrean a una tasa muy alta y se envían al sitio web en menos de un segundo).

- Ver datos agregados para un rol específico; por ejemplo, el servidor front-end, el servidor de mediación, el servidor perimetral, etc.

- Desplácese hacia abajo para ver los datos de sitios específicos, agrupaciones específicas dentro del sitio y, a continuación, servidores específicos dentro de la agrupación.

- Crear gráficos personalizados para que se muestren los contadores elegidos de forma predeterminada.

- Zoom y panorámica en los ejes x e y o solo en el eje x.

- Use intervalos de fechas o puntos en el tiempo para filtrar datos.

- Ver el rendimiento del servidor basado en indicadores de estado clave establecidos (KHIs). KHIs representa una colección de contadores de rendimiento con un rango correcto definido.

- Ver métricas detalladas de cada contador.

- Comparar datos entre varios poblaciones o servidores.

- Ver los informes latentes para identificar agentes que no están notificando los datos actuales al servicio de panel.

- Guardar una instancia determinada de datos del gráfico en un archivo.

- Ver KHIs en tiempo real, incluidas las actualizaciones. Si la vista historial está habilitada, solo se muestran los errores nuevos.

  - Ver todos los KHIs a la vez

  - Ver KHIs por servidor (vista horizontal)

  - Ver definiciones de KHI

## <a name="whats-new-in-release-20"></a>Novedades de la versión 2,0
<a name="BKMK_WhatsNew"> </a>

A continuación se describen las novedades de la versión 2,0. Si ya tiene una implementación de Statistics Manager y aún no la ha actualizado, consulte actualizar el [Administrador de estadísticas para Skype empresarial Server](upgrade.md).

- Se han agregado vistas de escenario para los escenarios de los extremos, la Health, la conmutación por error y el registro.

- Se han agregado muchos contadores nuevos para servidores SQL, más contadores de uso de Skype empresarial, etc.

- Integración del nodo de monitor para el agente del administrador de estadísticas: Si el agente está instalado en un nodo de supervisor, notificará las estadísticas de transacción sintéticas a los contadores como recuentos al administrador de estadísticas.

- Numerosas mejoras de confiabilidad y rendimiento.

Para comprobar la versión del sitio web de statistic Manager que está ejecutando:

- En el explorador de archivos, abra (directorio predeterminado) C:\Archivos de Files\Skype para Business Server StatsMan WebSite\bin

- Haga clic con el botón secundario en StatsManHubWebSite. dll y vea sus propiedades

- La versión del producto se mostrará en los detalles de Descripción.

## <a name="components"></a>Components
<a name="BKMK_Components"> </a>

Statistics Manager consta de los siguientes componentes:

- **Transportista.** Un agente liviano que se ejecuta en cada servidor supervisado. El agente permite sondeo configurable de alta tasa de contadores de rendimiento con agregación local.

- **Escucha.** La API del servidor que recibe datos de todos los agentes y agrega datos entre los mismos.

- **Perimetral.** Actúa como la API de cliente para el sistema, se ejecuta en los servidores web y proporciona actualizaciones de datos en tiempo real a clientes conectados a través del sitio Web. (El concentrador se instala automáticamente como parte del MSI del sitio web).

- **Página.** Una interfaz de usuario que reúne todas las características disponibles en el sistema.

Además, statistic Manager requiere **Redis**, un servidor de estructura de datos de código abierto para la caché en memoria. Para obtener más información sobre cómo descargar Redis, consulte [implementar el administrador de estadísticas](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Implementación local
<a name="BKMK_DeploymentOptions"> </a>

En una implementación local, un único servidor hospeda todos los componentes del administrador de estadísticas del servidor.

En el siguiente diagrama se muestra una implementación local en la que el sitio web del administrador de estadísticas, Hub, escucha y sistema de caché en Redis se hospedan en un solo equipo. Statistic Manager está supervisando tres servidores de Skype empresarial, cada uno de los cuales transmite los datos de un único agente a la escucha. Los usuarios se conectan a un solo sitio web para ver todos los datos agregados por statistic Manager:

![Implementación local del administrador de estadísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Requisitos
<a name="BKMK_Requirements"> </a>

Antes de implementar statistic Manager, tendrá que tener en cuenta los siguientes requisitos de software, de red y de hardware.

### <a name="software-requirements"></a>Requisitos de software

- Windows Server 2016 y 2019

- IIS (instalado automáticamente)

- Redis

- Servicios de administración de estadísticas (instalados automáticamente)

- PSExec: se necesita para realizar la implementación de agentes remotos

- .NET 4,5 (incluido con 2012 R2): necesario para los agentes y componentes del servidor
- Descargar [Skype empresarial Server, administrador de estadísticas en tiempo real (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Requisitos de red


|**Servidor de hospedaje**|**Agentes.**|**Escucha**|
|:-----|:-----|:-----|
|Una red Gigabit dúplex completa mínima.  <br/> |Puerto TCP saliente 8443 (número de Puerto personalizable) para comunicarse con el agente de escucha.  <br/> |El puerto de escucha debe ser el mismo en todos los servidores.  <br/> |
|Puerto TCP entrante 80 o 443 abierto para hospedar el sitio Web.  <br/> |||
|Puerto TCP entrante 8443 (número de Puerto personalizable) para que los agentes se comuniquen con él.  <br/> |||

Durante la instalación, se crean automáticamente puertos de Firewall para el agente de escucha y el sitio Web. Para los agentes, la instalación supone que las conexiones TCP salientes están permitidas de forma predeterminada.

### <a name="hardware-requirements"></a>Requisitos de hardware

En una implementación local, en la que un único servidor hospeda a todos los componentes del administrador de estadísticas del servidor, un servidor con 16 GB de RAM y 4 CPU debe poder admitir aproximadamente 150 muestras por segundo por segundo. Para determinar cuántos contadores/agentes puede admitir, use el siguiente cálculo:

100 servidores \*80 contadores \* 1 ejemplo por minuto de cada agente/60 segundos = ~ 133 muestras por segundo.

## <a name="security-considerations"></a>Consideraciones de seguridad
<a name="BKMK_Security"> </a>

Todo el tráfico entre los servidores está cifrado.

- El tráfico HTTPS cifrado se enviará a través del puerto 8443 (de forma predeterminada) desde el agente al servidor de escucha.

- El agente verificará la huella digital SSL en el servidor para asegurarse de que el servidor de escucha sea el destinatario esperado. Tenga en cuenta que el agente usa verificación de certificados por huella digital (en lugar de verificación en cadena). No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados.

- Una vez que el agente está satisfecho, el oyente es auténtico, el agente que comprueba la contraseña será presentado por el agente de escucha.

- El agente comienza a transmitir datos de rendimiento a través de la conexión a la escucha.

## <a name="for-more-information"></a>Más información
<a name="BKMK_Security"> </a>

Para obtener más información, vea los artículos siguientes:

- [Implementar el administrador de estadísticas para Skype Empresarial Server](deploy.md)

- [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md)

- [Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md)
