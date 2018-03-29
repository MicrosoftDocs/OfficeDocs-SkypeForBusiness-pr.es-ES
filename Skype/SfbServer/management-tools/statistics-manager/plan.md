---
title: Plan para el Gestor de estadísticas de Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/23/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumen: Leer este tema para aprender sobre el Gestor de estadísticas de Skype para Business Server 2015.'
ms.openlocfilehash: 63f064f9a6632250f3cfadddbcbb5fca2120f07b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server-2015"></a>Plan para el Gestor de estadísticas de Skype para Business Server 2015
 
**Resumen:** Lea este tema para aprender sobre el Gestor de estadísticas de Skype para Business Server 2015.
  
 Administrador de estadísticas de Skype para Business Server es una eficaz herramienta que permite ver Skype para los datos de rendimiento y la salud de Business Server en tiempo real. Puede sondear los datos de rendimiento a través de cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio Web del Administrador de estadísticas.
  
Puede utilizar Administrador de estadísticas para identificar problemas de rendimiento en curso, ver los resultados de un cambio planificado para su entorno, realizar un seguimiento de la resolución de las interrupciones y mucho más. Fuera de la caja, Gestor de estadísticas está configurado con umbrales del indicador de estado de clave (KHI) y pueden personalizarse para satisfacer las necesidades únicas de su implementación. 
  
Gestor de estadísticas se pueden implementar en una implementación de local en la que un único servidor aloja todos los componentes del Administrador de las estadísticas del servidor. Para obtener más información acerca de cómo implementar el Gestor de estadísticas, vea [Implementar Administrador de estadísticas de Skype para Business Server 2015](deploy.md). Si ya tiene una implementación existente de gestor de estadísticas, pero aún no ha actualizado a la versión 1.1, vea [Novedades de versión 1.1](plan.md#BKMK_WhatsNew) y [Actualizar estadísticas Administrador de Skype para Business Server 2015](upgrade.md).
  
Este tema incluye las secciones siguientes:
  
- [Características y funciones](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)
    
- [Novedades de la versión 1.1](plan.md#BKMK_WhatsNew)
    
- [Componentes](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)
    
- [Implementación local](plan.md#BKMK_DeploymentOptions)
    
- [Requisitos](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)
    
- [Consideraciones de seguridad](plan.md#BKMK_Security)
    
## <a name="features-and-capabilities"></a>Características y funciones
<a name="BKMK_Features"> </a>

Gestor de estadísticas le permite:
  
- Ver los datos sin procesar para todos los servidores en tiempo real. (Datos se muestrean a una velocidad muy alta y enviados al sitio Web en menos de un segundo.)
    
- Ver los datos que se agregan a una función específica; Por ejemplo, servidor Front-End, servidor de mediación, servidor perimetral y así sucesivamente.
    
- Profundizar para ver datos de sitios específicos, grupos específicos dentro del sitio y servidores específicos, a continuación, en la agrupación.
    
- Crear gráficos personalizados para que elige los contadores aparecen de forma predeterminada.
    
- Zoom y panorámica en ambos los ejes x e y- o en el eje x únicamente.
    
- Utilizar rangos de fechas o puntos en el tiempo para filtrar los datos. 
    
- Ver el rendimiento del servidor basándose en indicadores clave de estado establecido (KHIs). KHIs representan un conjunto de contadores de rendimiento con un rango saludable definido. 
    
- Ver las métricas detalladas para cada contador.
    
- Comparar datos entre varios servidores o poblaciones.
    
- Ver informes de contador latente para identificar los agentes que no están reportando datos actuales para el servicio de escritorio.
    
- Guardar una instancia determinada de los datos del gráfico en un archivo.
    
- KHIs vista en tiempo real, incluidas las actualizaciones. Si está habilitada la vista Historial, se muestran sólo los nuevos errores.
    
  - Ver al mismo tiempo todos los KHIs
    
  - Ver KHIs por servidor (vista horizontal)
    
  - Definiciones de vista KHI
    
## <a name="whats-new-in-release-11"></a>Novedades de la versión 1.1
<a name="BKMK_WhatsNew"> </a>

A continuación describen qué es lo nuevo en la versión 1.1. Si tiene una implementación existente de estadísticas Manager y aún no ha realizado la actualización, vea [Actualizar estadísticas Administrador de Skype para Business Server 2015](upgrade.md).
  
- Vistas del escenario se han agregado para medios de borde, tela de salud, grupo de conmutación por error y escenarios de registro.
    
- PerfAgentStorageManager.exe línea de comandos (que se instala con el agente de escucha) pueden exportar los datos del contador como un CSV.
    
- Muchos contadores nuevos se han agregado servidores SQL, más contadores Fabric de Windows, más Skype para contadores de uso del negocio y así sucesivamente.
    
- Integración de nodo supervisora para el agente Administrador de estadísticas - si el agente está instalado en un nodo supervisora, informará de las estadísticas de transacciones sintéticas como contadores de volver al administrador de estadísticas.
    
- Numerosas mejoras de confiabilidad y rendimiento.
    
Para comprobar la versión del sitio Web del Administrador de estadísticas está ejecutando:
  
- En el Explorador de archivos, abrir (el directorio por defecto) C:\Program Files\Skype para Business Server StatsMan WebSite\bin
    
- Haga clic con el botón secundario en StatsManHubWebSite.dll y ver sus propiedades
    
- La versión del producto se mostrará en los detalles de Descripción.
    
## <a name="components"></a>Components
<a name="BKMK_Components"> </a>

Gestor de estadísticas consta de los siguientes componentes:
  
- **Agente.** Un agente ligero que se ejecuta en cada servidor supervisado. El agente permite sondeo configurables alta tasa de contadores de rendimiento con la agregación local.
    
- **Agente de escucha.** La API del lado servidor que recibe los datos de todos los agentes y agrega los datos a través de las poblaciones.
    
- **Concentrador.** Sirve como la API de cliente para el sistema, se ejecuta en los servidores web y proporciona las actualizaciones de datos en tiempo real a los clientes conectados a través del sitio Web. (El concentrador se instala automáticamente como parte del sitio Web msi).
    
- **Sitio Web.** Una interfaz de usuario que reúne todas las características disponibles en el sistema.
    
Además, el Administrador de estadísticas requiere **Redis**, un servidor de estructura de datos de código abierto para el almacenamiento en caché en memoria. Para obtener más información acerca de cómo descargar Redis, vea [Implementar Gestor de estadísticas](deploy.md#BKMK_Deploy) .
  
## <a name="on-premises-deployment"></a>Implementación local
<a name="BKMK_DeploymentOptions"> </a>

En una implementación local, un único servidor aloja todos los componentes del Administrador de las estadísticas del servidor. 
  
El diagrama siguiente muestra una implementación local, en la que el sitio Web del Administrador de estadísticas, concentrador, escucha y Redis caché sistema se alojan en un solo equipo. Gestor de estadísticas está supervisando tres Skype para servidores empresariales, cada uno de los cuales tiene un solo agente de transmisión de datos a la escucha. Los usuarios conectarse a un solo sitio Web para ver todos los datos agregados por el Administrador de estadísticas:
  
![Implementación local del administrador de estadísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)
  
## <a name="requirements"></a>Requisitos
<a name="BKMK_Requirements"> </a>

Debe tener en cuenta los siguientes requisitos de hardware, redes y software antes de implementar Administrador de estadísticas. 
  
### <a name="software-requirements"></a>Requisitos de software

- Windows Server 2012 R2
    
- IIS (instalados automáticamente)
    
- Redis
    
- Servicios de gestor de estadísticas (instalados automáticamente)
    
- PSExec - necesario para realizar el despliegue del agente remoto
    
- 4.5 de .NET (incluido con 2012 R2) - necesario para los componentes del servidor
    
- .NET 4.0 - requerido para agentes
    
### <a name="networking-requirements"></a>Requisitos para redes


|**Servidor de alojamiento**|**Agentes.**|**Agente de escucha**|
|:-----|:-----|:-----|
|Red gigabit mínimo dúplex completo.  <br/> |Puerto TCP saliente 8443 (número de puerto personalizables) para comunicarse con el agente de escucha.  <br/> |El puerto de escucha debe ser el mismo en todos los servidores.  <br/> |
|El puerto TCP 80 o 443 abierto para alojar el sitio Web de entrada.  <br/> |||
|Puerto TCP 8443 (número de puerto personalizable) de entrada de los agentes para comunicarse con él.  <br/> |||
   
Durante la instalación, se crean automáticamente los puertos de firewall para la escucha y el sitio Web. Para los agentes, la instalación supone que se permiten las conexiones TCP salientes de forma predeterminada.
  
### <a name="hardware-requirements"></a>Requisitos de hardware

En una implementación local, en la que un único servidor aloja todos los componentes de administrador de las estadísticas del servidor, un servidor con 16 GB de RAM y 4 CPU debe ser capaz de admitir en promedio unos 150 muestras por segundo. Para determinar cuántos contadores/agentes puede admitir, utilice el siguiente cálculo: 
  
100 servidores \*80 contadores \* 1 ejemplo por minuto de cada agente / 60 segundos = ~ 133 muestras por segundo.
  
## <a name="security-considerations"></a>Consideraciones de seguridad
<a name="BKMK_Security"> </a>

Se cifra todo el tráfico entre servidores. 
  
- Tráfico HTTPS cifrado se enviará por el puerto 8443 (por defecto) desde el agente al servidor de agente de escucha.
    
- El agente comprobará la huella digital SSL en el servidor para asegurarse de que el servidor de agente de escucha es el destinatario previsto. Tenga en cuenta que el agente usa verificación de certificados por huella digital (en lugar de verificación en cadena). No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados.
    
- Una vez satisfecho el agente el agente de escucha es auténtico, una contraseña será presentada por el agente que después es confirmado por el agente de escucha. 
    
- El agente comienza a transmitir datos de rendimiento a través de la conexión con el agente de escucha.
    
## <a name="for-more-information"></a>Más información
<a name="BKMK_Security"> </a>

Para obtener más información, consulte lo siguiente:
  
- [Implementar el administrador estadísticas de Skype para Business Server 2015](deploy.md)
    
- [Actualizar estadísticas Administrador de Skype para Business Server 2015](upgrade.md)
    
- [Solucionar problemas de administrador de estadísticas de Skype para Business Server 2015](troubleshoot.md)
    
- [Skype para blog Business Manager de estadísticas de servidor](https://blogs.technet.microsoft.com/skypestatsman/)
    

