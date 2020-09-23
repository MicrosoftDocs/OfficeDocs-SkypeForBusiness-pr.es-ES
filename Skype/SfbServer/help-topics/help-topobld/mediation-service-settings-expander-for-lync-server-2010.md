---
title: Expansor de configuración del servicio de mediación para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Para editar las propiedades del servicio de mediación, defina las propiedades siguientes:'
ms.openlocfilehash: 51fbd889d7e9d673fb75b1062a70ae55a9f8585c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215111"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b5302-103">Expansor de configuración del servicio de mediación para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b5302-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b5302-104">Para editar las propiedades del servicio de mediación, defina las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5302-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="b5302-p101">**Puertos de escucha**: defina el puerto **TLS** en el que va a escuchar el servicio de mediación. De forma predeterminada, el valor del puerto el TCP 5067 mediante seguridad de la capa de transporte (TLS)</span><span class="sxs-lookup"><span data-stu-id="b5302-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="b5302-p102">Opcionalmente, puede definir un valor de puerto **TCP**. El valor predeterminado es TCP 5068.</span><span class="sxs-lookup"><span data-stu-id="b5302-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b5302-p103">Para habilitar la configuración del valor de puerto TCP, seleccione **Habilitar puerto TCP**. Consulte la documentación de su puerta de enlace de red telefónica conmutada (RTC) o de la central de conmutación privada mediante protocolo de Internet (IP-PBX) para obtener información sobre los requisitos de configuración del puerto necesarios para comunicarse con el servicio de mediación.</span><span class="sxs-lookup"><span data-stu-id="b5302-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="b5302-111">Seleccione **Habilitar puerto TCP** para definir el valor de puerto de las comunicaciones TCP de una puerta de enlace RTC o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="b5302-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="b5302-112">Una lista del **Tronco** (es decir, troncos del protocolo de inicio de sesión (SIP), la **Puerta de enlace** (puerta de enlace RTC o IP-PBX) y el **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y los asociados actualmente.</span><span class="sxs-lookup"><span data-stu-id="b5302-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="b5302-p104">Seleccione un Tronco, una Puerta de enlace y un Sitio y haga clic en **Convertir en predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **Eliminar predeterminado** para eliminar la selección de los valores predeterminados. A continuación debe seleccionar un nuevo valor predeterminado y hacer clic en **Convertir en predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="b5302-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="b5302-116">**Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b5302-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b5302-117">**Cancelar** Descarta los cambios y cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b5302-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b5302-118">**Ayuda** Muestra la ayuda de esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="b5302-118">**Help** Displays this help screen.</span></span>
  

