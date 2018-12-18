---
title: Plan para el Administrador de estadísticas de Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumen: Lea este tema para obtener más información acerca del Administrador de estadísticas de Skype para Business Server.'
ms.openlocfilehash: a73e58acdd91b4112537fa0028bf2c134e9c0fce
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297861"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Plan para el Administrador de estadísticas de Skype para Business Server

**Resumen:** Lea este tema para obtener más información acerca del Administrador de estadísticas de Skype para Business Server.

 Administrador de estadísticas de Skype para Business Server es una herramienta eficaz que le permite ver Skype para los datos de estado y rendimiento de servidor empresarial en tiempo real. Puede sondear los datos de rendimiento a través de cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio Web de estadísticas de administrador.

Puede usar el Administrador de estadísticas para identificar problemas de rendimiento en curso, ver los resultados de un cambio planeado a su entorno, realizar un seguimiento de resolución de interrupciones y mucho más. Fuera del cuadro, Administrador de estadísticas está configurado con los umbrales de indicador de estado de clave (KHI) y se puede personalizar para adaptarse a necesidades específicas de la implementación.

Puede implementar las estadísticas de administrador en una implementación local en la que un único servidor hospeda todos los componentes de estadísticas administrador del servidor. Para obtener más información sobre la implementación de las estadísticas de administrador, vea [Implementar el Administrador de estadísticas de Skype para Business Server](deploy.md). Si ya tiene una implementación existente de las estadísticas de administrador, pero aún no ha actualizado a la versión 2.0, vea [¿Qué es nuevo en la versión 2.0](plan.md#BKMK_WhatsNew) y [Actualizar las estadísticas de administrador de Skype para Business Server](upgrade.md).

Este tema incluye las secciones siguientes:

- [Características y funciones](plan.md#BKMK_Features)

- [¿Qué es nuevo en la versión 2.0](plan.md#BKMK_WhatsNew)

- [Componentes](plan.md#BKMK_Components)

- [Implementación local](plan.md#BKMK_DeploymentOptions)

- [Requisitos](plan.md#BKMK_Requirements)

- [Consideraciones de seguridad](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Características y funciones
<a name="BKMK_Features"> </a>

Administrador de estadísticas le permite:

- Ver datos sin procesar para todos los servidores en tiempo real. (Datos se muestrea a una tasa muy alta y enviados al sitio Web en menos de un segundo.)

- Ver los datos que se agregan a un rol específico; Por ejemplo, servidor Front-End, el servidor de mediación, servidor perimetral y así sucesivamente.

- Explorar en profundidad datos de vista para sitios específicos, grupos de servidores específicos dentro del sitio y servidores específicos, a continuación, dentro del grupo.

- Crear gráficos personalizados para que elegido contadores se muestran de forma predeterminada.

- Zoom y panorámica en ambos los ejes x e y- o en el eje x únicamente.

- Usar los intervalos de fechas o puntos en el tiempo para filtrar los datos.

- Ver el rendimiento del servidor en función de indicadores clave de estado establecido (KHIs). KHIs representan una colección de contadores de rendimiento con un rango definido correcto.

- Ver las métricas detalladas de cada contador.

- Comparar datos en varios servidores o poblaciones.

- Visualización de informes de contador latente para identificar a los agentes que no son informes de datos actuales para el servicio de panel.

- Guardar una instancia determinada de los datos del gráfico en un archivo.

- Vista KHIs en tiempo real, incluidas las actualizaciones. Si está habilitada la vista Historial, se muestran sólo los errores de nuevo.

  - Ver todos los KHIs a la vez

  - Ver KHIs por servidor (vista horizontal)

  - Definiciones de vista KHI

## <a name="whats-new-in-release-20"></a>¿Qué es nuevo en la versión 2.0
<a name="BKMK_WhatsNew"> </a>

El siguiente describe cuáles son las novedades en la versión 2.0. Si tiene una implementación existente del Administrador de estadísticas y aún no se ha realizado la actualización, vea [Actualizar administrador de estadísticas de Skype para Business Server](upgrade.md).

- Se han agregado las vistas de escenario para medios perimetrales, estado de Fabric, conmutación por error y escenarios de registro.

- Muchos contadores nuevos se han agregado servidores SQL Server, más Skype para contadores de uso empresarial y así sucesivamente.

- Integración de nodo de monitor para el agente de administrador de estadísticas - si el agente está instalado en un nodo de monitor, informará de las estadísticas de transacciones sintéticas como contadores de vuelta al administrador de estadísticas.

- Numerosas mejoras de rendimiento y confiabilidad.

Para comprobar la versión del sitio Web de estadísticas de administrador está ejecutando:

- En el Explorador de archivos, abra (directorio predeterminado) C:\Program Files\Skype para Business Server StatsMan WebSite\bin

- Haga clic con el botón secundario en StatsManHubWebSite.dll y ver sus propiedades

- La versión del producto se mostrará en los detalles de Descripción.

## <a name="components"></a>Components
<a name="BKMK_Components"> </a>

Administrador de estadísticas consta de los siguientes componentes:

- **Agente.** Un agente ligero que se ejecuta en cada servidor supervisado. El agente permite sondeo configurable alta tasa de contadores de rendimiento con agregación local.

- **Agente de escucha.** La API de lado servidor que recibe los datos de todos los agentes y agrega datos a través de poblaciones.

- **Concentrador.** Actúa como la API de cliente para el sistema, se ejecuta en los servidores web y proporciona las actualizaciones de datos en tiempo real a los clientes conectados a través del sitio Web. (El concentrador se instala automáticamente como parte del sitio Web msi).

- **Sitio Web.** Una interfaz de usuario que reúne todas las características disponibles en el sistema.

Además, el Administrador de estadísticas requiere **Redis**, un servidor de estructura de datos de origen para abrir para almacenar en caché en memoria. Para obtener más información acerca de cómo descargar Redis, vea [Implementar el Administrador de estadísticas](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Implementación local
<a name="BKMK_DeploymentOptions"> </a>

En una implementación local, un único servidor hospeda todos los componentes de estadísticas administrador del servidor.

En el siguiente diagrama se muestra una implementación local, en el que se hospedan el sitio Web del Administrador de estadísticas, concentrador, agente de escucha y Redis almacenamiento en memoria caché del sistema en un solo equipo. Administrador de estadísticas está supervisando tres Skype para servidores empresariales, cada uno de los cuales tiene un único agente de transmisión de datos a la escucha. Los usuarios se conectan a un solo sitio Web para ver todos los datos agregados por el Administrador de estadísticas:

![Implementación local del administrador de estadísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Requisitos
<a name="BKMK_Requirements"> </a>

Debe tener en cuenta los siguientes requisitos de hardware, redes y software antes de implementar las estadísticas de administrador.

### <a name="software-requirements"></a>Requisitos de software

- Windows Server 2016 y 2019

- IIS (instalados automáticamente)

- Redis

- Servicios de administrador de estadísticas (instalados automáticamente)

- PSExec - necesario para realizar la implementación de agentes remotos

- .NET 4.5 (incluido con 2012 R2) - necesario para los agentes y componentes de servidor
- Descargar el [Skype para Business Server, el Administrador de estadísticas en tiempo real (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Requisitos de red


|**Servidor de hospedaje**|**Agentes.**|**Agente de escucha**|
|:-----|:-----|:-----|
|La red de gigabit mínimo dúplex completo.  <br/> |Puerto TCP saliente 8443 (número de puerto personalizable) para comunicarse con el agente de escucha.  <br/> |El puerto de escucha debe ser el mismo en todos los servidores.  <br/> |
|El puerto TCP 80 o 443 abierto para hospedar el sitio Web de entrada.  <br/> |||
|El puerto TCP 8443 (número de puerto personalizable) de entrada para que los agentes para comunicarse con él.  <br/> |||

Durante la instalación, se crean automáticamente los puertos de firewall para el agente de escucha y el sitio Web. Para los agentes, la instalación se da por supuesto que se permiten las conexiones TCP salientes de forma predeterminada.

### <a name="hardware-requirements"></a>Requisitos de hardware

En una implementación local, en la que un único servidor hospeda todos los componentes de administrador de las estadísticas del servidor, un servidor con 16 GB de RAM y 4 de la CPU debe ser capaz de admitir aproximadamente 150 muestras por segundo en promedio. Para determinar cuántos contadores/agentes puede admitir, use el siguiente cálculo:

100 servidores \*contadores de 80 \* 1 ejemplo por minuto de cada agente / 60 segundos = ~ 133 muestras por segundo.

## <a name="security-considerations"></a>Consideraciones de seguridad
<a name="BKMK_Security"> </a>

Se cifra todo el tráfico entre servidores.

- Tráfico HTTPS cifrado se enviarán a través del puerto 8443 (de forma predeterminada) del agente de en el servidor de agente de escucha.

- El agente de comprobará si la huella digital SSL en el servidor para asegurarse de que el servidor de agente de escucha es el destinatario previsto. Tenga en cuenta que el agente usa verificación de certificados por huella digital (en lugar de verificación en cadena). No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados.

- Después de que el agente esté satisfecho el agente de escucha es auténtico, se le presentará una contraseña por el agente que, a continuación, se comprueba el agente de escucha.

- El agente de comienza la transmisión de datos de rendimiento a través de la conexión con el agente de escucha.

## <a name="for-more-information"></a>Para más información
<a name="BKMK_Security"> </a>

Para obtener más información, consulte lo siguiente:

- [Implementar el Administrador de estadísticas de Skype para Business Server](deploy.md)

- [Actualizar el Administrador de estadísticas de Skype para Business Server](upgrade.md)

- [Solucionar problemas de administrador de estadísticas de Skype para Business Server](troubleshoot.md)
