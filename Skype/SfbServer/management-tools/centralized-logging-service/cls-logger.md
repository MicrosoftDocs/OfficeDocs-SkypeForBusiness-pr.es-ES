---
title: Registrador de CLS para Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/25/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Summary: Learn how to use the Centralized Logging Service (CLS) Logger in Skype Empresarial Server 2015.'
ms.openlocfilehash: dbe8ef417eb702943c76214be492151ee4d1dac7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862187"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>Registrador de CLS para Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo usar el registrador del servicio de registro centralizado (CLS) en Skype Empresarial Server 2015.
  
El registrador cls es una herramienta que le ayuda a administrar los registros generados por el servicio de registro centralizado.
  
## <a name="prerequisites"></a>Requisitos previos

Para usar correctamente el registrador de CLS, deberá asegurarse de que se cumplen los siguientes requisitos:
  
- Está usando la herramienta en un equipo que es miembro del dominio en el que se ejecuta el Servicio de registro centralizado (CLS). La herramienta no se admite actualmente en sesiones remotas de PowerShell.
    
- El archivo Default.tmx de la carpeta de seguimiento (la carpeta donde se capturan los datos de seguimiento para CLS) y Snooper deben copiarse en la misma carpeta donde está instalada la herramienta clslogger.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Comprobar el estado de registro de un conjunto de grupos o equipos

Use los siguientes comandos para comprobar el estado del registro:
  
1. En la pestaña "Escenarios de inicio/detenerse", seleccione una agrupación de grupos o equipos en la vista de árbol topología.
    
2. Haga clic en el botón Estado de registro.
    
3. Vea el resultado del comando en el área De salida de comandos de PowerShell para obtener información específica sobre el estado de registro de los grupos de servidores o equipos seleccionados.
    
## <a name="start-an-existing-scenario"></a>Iniciar un escenario existente

Para iniciar un escenario existente:
  
1. En la pestaña "Escenarios de inicio/detenerse", seleccione un escenario existente en el menú desplegable Escenarios.
    
2. Seleccione una agrupación de grupos o equipos en la vista de árbol topología.
    
3. Haga clic en el botón Iniciar escenario. La interfaz de usuario se deshabilitará hasta que se complete la operación. Esto puede ser lento en implementaciones grandes.
    
4. La interfaz de usuario se habilitará de nuevo una vez que el escenario se haya iniciado correctamente, los detalles de la acción también se mostrarán en el área De salida de comandos de PowerShell.
    
5. La tarea puede tardar algún tiempo antes en que CLS recoga el registro antes de los nuevos datos de este escenario.
    
## <a name="stop-an-existing-scenario"></a>Detener un escenario existente

Para detener un escenario existente:
  
1. En la pestaña "Escenarios de inicio/detenerse", seleccione un escenario existente en el menú desplegable Escenarios.
    
2. Seleccione una agrupación de grupos o equipos en la vista de árbol topología.
    
3. Haga clic en el botón Detener escenario. La interfaz de usuario se deshabilitará hasta que se complete la operación. Esto puede ser lento en implementaciones grandes.
    
4. La interfaz de usuario se habilitará de nuevo una vez que el escenario se haya detenido, los detalles de la acción también se mostrarán en el área De salida de comandos de PowerShell.
    
![Inicio y detenerse del registrador CLS.](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Buscar registros

Para buscar registros, seleccione la pestaña "Registros cls de búsqueda" y haga clic en el botón "Registros de búsqueda" después de rellenar los campos mostrados como se describe a continuación:
  
> **Carpeta de archivos de registro** Carpeta para guardar los resultados de la búsqueda de registro. (Obligatorio)
> 
> **Nivel de registro** Esto determina el nivel más bajo que se mostrará en los resultados. Por ejemplo, si se selecciona Advertencia, solo se mostrará Advertencia, Error y Fatal. El valor predeterminado es Depurar.
> 
> **Grupos de servidores** Grupos de equipos en los que realizar la búsqueda de registro, estos son los nodos primarios de la vista de árbol. (Obligatorio)
> 
> **Equipos** Equipos individuales en los que realizar la búsqueda de registro, estos son todos los nodos secundarios de la vista de árbol. (Obligatorio)
> 
> **Hora de inicio** Período de tiempo desde el que CLS consultará los registros. (Obligatorio)
> 
> **Hora de finalización** Período de tiempo desde el que CLS dejará de consultar los registros. (Obligatorio)
> 
> **Componentes** Se usa para seleccionar los componentes que se agregarán a la consulta. (Opcional)
> 
> **Id. de llamada** Identificador de llamada de los cuadros de diálogo SIP que se filtrarán. Tenga en cuenta que este campo usa coincidencia exacta. (Opcional)
> 
> **Id. de conferencia** El identificador de conferencia de las conferencias por las que se va a filtrar. Tenga en cuenta que este campo usa coincidencia exacta. (Opcional)
> 
> **Dirección IP** La dirección IP que se va a filtrar. Tenga en cuenta que este campo usa coincidencia exacta. (Opcional)
> 
> **Identificadores de correlación** Trace statements that are logically linked together by this ID. (Opcional)
> 
> **Teléfono número** Filtrar por número de teléfono. (Opcional)
> 
> **URI de SIP** Filtrar por URI de SIP. (Opcional)
> 
> **Contenido del mensaje SIP contiene** Filtrar por contenido de mensaje SIP, esto subcadena búsqueda dentro de este campo. (Opcional)
> 
> **Coincidencia de cualquiera** Busca con un or lógico si está activado. El valor predeterminado es Coincidencia exacta de todos los parámetros.
> 
> **Omitir registros de red** Omite la búsqueda en los registros de red si está activada.
    
![Registros de búsqueda del registrador cls.](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Crear un escenario

1. En la **pestaña Editar escenarios,** haga clic en **el botón Crear** escenario.
    
    > [!NOTE]
    > La creación de un nuevo escenario clonará la configuración del escenario que está seleccionado actualmente. Si hace clic **en Borrar Configuración** antes de crear un nuevo escenario, empezará sin componentes ni marcas seleccionadas.
  
2. Escriba el nombre del escenario que desea crear y presione la tecla Entrar o haga clic en el botón Aceptar.
    
3. Ahora se creará el nuevo escenario. Una vez creada correctamente, la lista desplegable Escenarios se seleccionará con el escenario recién creado.
    
## <a name="modify-a-scenario"></a>Modificar un escenario

![CLS Logger Screen shot, edit scenarios.](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. En la **pestaña Editar escenarios,** busque el escenario que desea modificar.
    
2. Realice los cambios deseados en los componentes, niveles y marcas.
    
3. Haga clic en **el botón Guardar escenario.**
    
4. Tras guardar correctamente el escenario, actualizará el panel de información del escenario con la configuración actualizada.
    
## <a name="delete-a-scenario"></a>Eliminar un escenario

1. En la **pestaña Editar escenarios,** seleccione un escenario existente en el menú desplegable Escenarios.
    
2. Haga **clic en Eliminar escenario** para eliminar el escenario.
    
3. Después de confirmar la acción, se eliminará el escenario.
    

