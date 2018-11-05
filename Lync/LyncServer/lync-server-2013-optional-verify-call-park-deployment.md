---
title: 'Lync Server 2013: (Opcional) Comprobar implementación del estacionamiento de llamadas'
TOCTitle: (Opcional) Comprobar la implementación del estacionamiento de llamadas
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48277292
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Opcional) Comprobar la implementación del estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-11_

Después de instalar y configurar el Estacionamiento de llamadas, debe comprobar la configuración para asegurarse de que la recuperación y el estacionamiento de llamadas funcionen según lo previsto. Como mínimo, compruebe los elementos siguientes:

  - Llame a un usuario que tenga habilitado el Estacionamiento de llamadas y haga que estacione la llamada.
    

    > [!NOTE]
    > Si ha habilitado el Estacionamiento de llamadas en la directiva de voz justo antes de realizar esta prueba, el usuario que estaciona la llamada debe cerrar la sesión de Lync Server y volver a iniciarla para que la opción Estacionamiento de llamadas se muestre en la lista de transferencia de llamadas.



  - Marque el número de órbita para recuperar la llamada.

  - Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.

