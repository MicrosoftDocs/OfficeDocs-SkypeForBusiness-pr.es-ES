---
title: Registrador de CLS para Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/25/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Resumen: Aprenda a usar el registrador del servicio de registro centralizado (CLS) en Skype empresarial Server 2015.'
ms.openlocfilehash: 496f30bdcedeb491bd5bfa211f08c04853b49bf8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274467"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>Registrador de CLS para Skype Empresarial Server 2015
 
**Resumen:** Aprenda a usar el registrador del servicio de registro centralizado (CLS) en Skype empresarial Server 2015.
  
CLS Logger es una herramienta que ayuda en la administración de los registros que genera el servicio de registro centralizado.
  
## <a name="prerequisites"></a>Requisitos previos

A fin de utilizar CLS Logger correctamente, es preciso asegurarse de lo siguiente:
  
- Está utilizando la herramienta en un equipo miembro del dominio donde se ejecuta el servicio de registro centralizado (CLS). Actualmente, la herramienta no es compatible en las sesiones remotas de PowerShell.
    
- Es necesario copiar el archivo Default.tmx de la carpeta de seguimiento (la carpeta donde se capturan los datos de seguimiento para CLS) y Snooper en la misma carpeta donde se encuentra instalada la herramienta CLS Logger.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Comprobar el estado de registro de un conjunto de grupos de servidores o equipos

Use el siguiente comando para comprobar el estado de registro:
  
1. En la pestaña "escenarios de inicio/parada", seleccione una agrupación de grupos o equipos en la vista de árbol de topología.
    
2. Haga clic en el botón Estado de registro.
    
3. Vea la salida del comando en el área de salida del comando de PowerShell para obtener detalles sobre el estado de registro de los equipos o los grupos de servidores seleccionados.
    
## <a name="start-an-existing-scenario"></a>Iniciar un escenario existente

Para iniciar un escenario existente:
  
1. En la pestaña "escenarios de inicio/parada", seleccione un escenario existente en el menú desplegable escenarios.
    
2. Seleccione una agrupación de equipos o grupos de servidores en la vista del árbol de la topología.
    
3. Haga clic en el botón Iniciar escenario. Hasta que no se complete la acción, se deshabilitará la interfaz de usuario. Es posible que este proceso sea lento en las implementaciones grandes.
    
4. Una vez que el escenario se haya iniciado correctamente, se habilitará nuevamente la interfaz de usuario; también se mostrarán los detalles de la acción en el área de salida del comando de PowerShell.
    
5. Es posible que la tarea demore algo de tiempo antes de que CLS recoja el registro antes de nuevos datos del escenario.
    
## <a name="stop-an-existing-scenario"></a>Detener un escenario existente

Para detener un escenario existente:
  
1. En la pestaña "escenarios de inicio/parada", seleccione un escenario existente en el menú desplegable escenarios.
    
2. Seleccione una agrupación de equipos o grupos de servidores en la vista del árbol de la topología.
    
3. Haga clic en el botón Detener escenario. Hasta que no se complete la acción, se deshabilitará la interfaz de usuario. Es posible que este proceso sea lento en las implementaciones grandes.
    
4. Una vez que el escenario se haya detenido correctamente, se habilitará nuevamente la interfaz de usuario; también se mostrarán los detalles de la acción en el área de salida del comando de PowerShell.
    
![Inicio y detención del registrador de CLS](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Buscar registros

Para buscar registros, seleccione la ficha "buscar registros de CLS" y haga clic en el botón "buscar registros" después de rellenar los campos mostrados como se describe a continuación:
  
> **Carpeta de archivos de registros** La carpeta para guardar los resultados de la búsqueda de registros. (Necesaria)
> 
> **Nivel de registro** Esto determina el nivel más bajo que se mostrará en los resultados; por ejemplo, si selecciona Advertencia, solo se mostrarán los errores irrecuperables, los errores y las advertencias. El nivel predeterminado es Depuración.
> 
> **Grupos** Los grupos de equipos en los que se realizará la búsqueda de registros. Estos son nodos primarios de la vista de árbol. (Necesarios)
> 
> **Equipos** Los equipos individuales en los que se realizará la búsqueda de registros. Estos son nodos secundarios de la vista de árbol. (Necesarios)
> 
> **Hora de inicio** El período de tiempo en el que CLS consultará los registros. (Necesaria)
> 
> **Hora de finalización** El período de tiempo en el que CLS detendrá la consulta de registros. (Necesaria)
> 
> **Componentes** Se utilizan para seleccionar qué componentes agregar a la consulta. (Opcional)
> 
> **Id. de llamada** El id. de llamada de todos los diálogos SIP que se utilizará como filtro. Tenga en cuenta que este campo utiliza resultados exactos. (Opcional)
> 
> **Id. de conferencia** El id. de conferencia de todas las conferencias que se utilizará como filtro. Tenga en cuenta que este campo utiliza resultados exactos. (Opcional)
> 
> **Dirección IP** La dirección IP que se utilizará como filtro. Tenga en cuenta que este campo utiliza resultados exactos. (Opcional)
> 
> **Id. de correlación** Realiza un seguimiento de las instrucciones lógicamente vinculadas en conjunto por este id. (Opcional)
> 
> **Número de teléfono** Filtra por número de teléfono. (Opcional)
> 
> **URI de SIP** Filtra por URI de SIP. (Opcional)
> 
> **El contenido del mensaje SIP contiene** Filtra por el contenido de los mensajes SIP; se realizarán búsquedas en las subcadenas del campo. (Opcional)
> 
> **Cualquier resultado** Las búsquedas usan un conector lógico O si se selecciona. Todos los parámetros se establecen de forma predeterminada en Coincidencia exacta.
> 
> **Omitir registros de red** Si se selecciona, se omiten todos los registros de red de la búsqueda.
    
![Registros de búsqueda del registrador de CLS](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Crear un escenario

1. En la pestaña **Editar escenarios** , haga clic en el botón **crear escenario** .
    
    > [!NOTE]
    > Crear un escenario clonará la configuración del escenario que esté seleccionado en ese momento. Si hace clic en **Borrar los ajustes** antes de crear un escenario empezará sin elementos ni marcas seleccionados.
  
2. Escriba el nombre del escenario que va a crear y presione la tecla Entrar o haga clic en el botón Aceptar.
    
3. Se creará el escenario. Tras la creación correcta, se seleccionará la lista desplegable Escenarios con el escenario recién creado.
    
## <a name="modify-a-scenario"></a>Modificar un escenario

![Captura de pantalla de CLS Logger, editar escenarios](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. 	En la ficha **Editar escenarios**, busque el escenario que desee modificar.
    
2. Realice los cambios que desee a los componentes, niveles y marcadores.
    
3. Haga clic en el botón **Guardar escenario**.
    
4. Tras guardar el escenario correctamente, se actualizará el panel de información del escenario con la configuración actualizada.
    
## <a name="delete-a-scenario"></a>Eliminar un escenario

1. 	En la ficha **Editar escenarios**, seleccione un escenario existente en el menú desplegable Escenarios.
    
2. Haga clic en **Eliminar escenario** para eliminar el escenario.
    
3. Después de confirmar la acción, el escenario se eliminará.
    

