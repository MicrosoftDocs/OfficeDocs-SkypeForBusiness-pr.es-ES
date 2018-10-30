---
title: "Lync Server 2013: Crear la directiva de enrutamiento VoIP para usuarios de sucursal"
TOCTitle: Crear la directiva de enrutamiento VoIP para usuarios de sucursal
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48274462
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear la directiva de enrutamiento VoIP para usuarios de sucursal en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-23_

Se recomienda crear una directiva de voz sobre IP (VoIP) independiente para los usuarios de las sucursales. Esta directiva deberá contener rutas para salir de la puerta de enlace de la Aplicación de sucursal con funciones de supervivencia o de la puerta de enlace externa del Servidor de sucursal con funciones de supervivencia y rutas de reserva para salir de una puerta de enlace del sitio central. Independientemente de dónde se registre el usuario, ya sea en el registrar de la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia, o bien en el clúster del registrar de reserva del sitio central, la directiva de VoIP del usuario permanece en vigor.

## Para configurar la directiva de enrutamiento VoIP para usuarios de sucursal

1.  Cree un plan de marcado de nivel de usuario y asígnelo a los usuarios de sucursal. (Vea [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md) en la documentación de operaciones.)

2.  Asigne normas de normalización que se correspondan con los hábitos de marcado de los usuarios de ese sitio. Si el usuario de la Aplicación de sucursal con funciones de supervivencia o del Servidor de sucursal con funciones de supervivencia se conmuta por error en el grupo de servidores del registrar del sitio central, entrará en vigor el mismo plan de marcado. (Consulte [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md) en la documentación de operaciones.)

3.  Configure una ruta de voz que salga de la puerta de enlace de la Aplicación de sucursal con funciones de supervivencia o de la puerta de enlace externa del Servidor de sucursal con funciones de supervivencia. (Vea [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md) en la documentación de operaciones.)

4.  Establezca una ruta de llamada de reserva en la puerta de enlace de la Aplicación de sucursal con funciones de supervivencia o del Servidor de sucursal con funciones de supervivencia para orientarla al grupo de servidores del registrar de reserva (combinado con el servidor de mediación) del sitio central. (Consulte la documentación del proveedor de la Aplicación de sucursal con funciones de supervivencia o del Servidor de sucursal con funciones de supervivencia.)
    

    > [!NOTE]
    > Esta configuración de la ruta de llamada de reserva garantiza que las llamadas entrantes para el usuario de la sucursal funcionarán cuando la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia no esté disponible (por ejemplo, si está inactivo por mantenimiento). Si el registrar y el servidor de mediación de la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia no están disponibles, y el usuario está registrado con el grupo de servidores del registrar de reserva en el sitio central, las llamadas entrantes seguirán llegando al usuario.



**Siguiente paso**: [Configurar los valores para volver a enrutar el correo de voz en Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

