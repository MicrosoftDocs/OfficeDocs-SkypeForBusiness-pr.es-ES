---
title: Expansor de configuración del servicio de mediación de Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Defina las siguientes propiedades para editar las propiedades del servicio de mediación:'
ms.openlocfilehash: d8529a97459de70270fbe709d06c92e5a1b37af3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="1f738-103">Expansor de configuración del servicio de mediación de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1f738-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="1f738-104">Defina las siguientes propiedades para editar las propiedades del servicio de mediación:</span><span class="sxs-lookup"><span data-stu-id="1f738-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="1f738-p101">**Puertos de escucha**: defina el puerto **TLS** en el que va a escuchar el servicio de mediación. El valor del puerto TCP es 5067 de forma predeterminada mediante Seguridad de la capa de transporte (TLS)</span><span class="sxs-lookup"><span data-stu-id="1f738-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="1f738-p102">Opcionalmente, puede definir un valor de puerto **TCP**. El valor predeterminado es TCP 5068.</span><span class="sxs-lookup"><span data-stu-id="1f738-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1f738-p103">Para habilitar la configuración del valor de puerto TCP, seleccione **Habilitar puerto TCP**. Mire la documentación de su puerta de enlace de red telefónica conmutada (RTC) o de la central de conmutación privada mediante protocolo de Internet (IP-PBX) para más información sobre los requisitos necesarios de configuración del puerto para comunicarse con el servicio de mediación.</span><span class="sxs-lookup"><span data-stu-id="1f738-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="1f738-111">Seleccione **Habilitar puerto TCP** para definir el valor de puerto de las comunicaciones TCP de una puerta de enlace RTC o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="1f738-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="1f738-112">Lista del **Tronco** (es decir, troncos SIP), **Puertas de enlace** (puerta de enlace RTC o IP-PBX) y **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y actualmente asociados.</span><span class="sxs-lookup"><span data-stu-id="1f738-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="1f738-p104">Seleccione un tronco, una puerta de enlace y un sitio y haga clic en **Establecer como predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **No establecer como predeterminado** para eliminar la selección de los valores predeterminados. Luego, necesitará seleccionar un nuevo valor predeterminado y hacer clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="1f738-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
 <span data-ttu-id="1f738-116">**Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1f738-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="1f738-117">**Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1f738-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="1f738-118">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="1f738-118">**Help** Displays this help screen.</span></span>
  

