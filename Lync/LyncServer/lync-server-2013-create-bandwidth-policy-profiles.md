---
title: Crear perfiles de directivas de ancho de banda en Lync Server 2013
TOCTitle: Crear perfiles de directivas de ancho de banda en Lync Server 2013
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48276206
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear perfiles de directivas de ancho de banda en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

Las *directivas de ancho de banda* definen limitaciones en el uso de ancho de banda para las modalidades de audio y vídeo en tiempo real. Las directivas de ancho de banda se aplican a los *perfiles de directiva de ancho de banda*, que pueden aplicarse a varios sitios de red para el control de admisión de llamadas.

Para obtener instrucciones sobre los límites de ancho de banda que debe definir en su implementación de control de admisión de llamadas, consulte [Definición de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) en la documentación referente a la planeación.

Para más información sobre cómo trabajar con directivas y perfiles de directiva de ancho de banda, consulte la documentación del Shell de administración de Lync Server para los cmdlets siguientes:

  - [New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

Las directivas de ejemplo creadas en el procedimiento siguiente definen límites para el tráfico de audio global, sesiones de audio individuales, el tráfico de vídeo global y sesiones de vídeo individuales. Por ejemplo, el perfil de directiva de ancho de banda 5Mb\_Link define los límites siguientes:

  - Límite de audio: 2.000 kbps

  - Límite de sesión de audio: 200 kbps

  - Límite de vídeo: 1.400 kbps

  - Límite de sesión de vídeo: 700 kbps


> [!NOTE]
> El valor de Límite de sesión de audio es 40 kbps. El valor de Límite de sesión de vídeo es 100 kbps.



## Para crear perfiles de directiva de ancho de banda mediante el Shell de administración

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Para cada perfil de directiva de ancho de banda que quiera crear, ejecute el cmdlet New-CsNetworkBandwidthPolicyProfile. Por ejemplo, ejecute lo siguiente:
    
    ```
    New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
    ```
    ```
    New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
    ```
    ```
    New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
    ```
    ```
    New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
    ```
    
## Para crear perfiles de directiva de ancho de banda mediante el Panel de control de Lync Server

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Perfil de directiva**.

4.  Haga clic en **Nuevo**.

5.  En la página **Nuevo perfil de directiva**, haga clic en **Nombre** y escriba un nombre para el perfil de directiva de ancho de banda.

6.  Haga clic en **Límite de audio** y escriba el número máximo de kbps que permitir para todas las sesiones de audio combinadas.

7.  Haga clic en **Límite de sesión de audio** y escriba el número máximo de kbps que permitir para cada sesión de audio.

8.  Haga clic en **Límite de vídeo** y escriba el número máximo de kbps que permitir para todas las sesiones de vídeo combinadas.

9.  Haga clic en **Límite de sesión de vídeo** y escriba el número máximo de kbps que permitir para cada sesión de vídeo.

10. Si lo desea, haga clic en **Descripción** y escriba información adicional para describir este perfil de directiva de ancho de banda.

11. Haga clic en **Confirmar**.

12. Para terminar de crear perfiles de directiva de ancho de banda para su topología, repita los pasos del 4 al 11 con la configuración para otros perfiles de directiva de ancho de banda.

