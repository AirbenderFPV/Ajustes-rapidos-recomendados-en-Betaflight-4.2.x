# Ajustes-rapidos-recomendados-en-Betaflight-4.2.x
Ajustes rapidos para Betaflight 4.2.x

Estos comandos son sugerencias sobre cómo se pueden ajustar algunas de las configuraciones menos comunes para adaptarse a un cierto tipo de vuelo.  
Son valores que Betaflight nos da como orientativos para los diferentes tipos de vuelo.   
No ajustaran perfecto nuestro quad, ya que no incluyen ajustes de PID o valores de filtro, pero nos ayudaran a tener un control mas adaptado a nuestras necesidades.

Para usar estos comandos tendremos que copiarlos y pegarlos en el CLI, una vez pegados le damos a enter.  
Para guardarlos tenemos que ejecutar el comando _Save_.

- ProRace (Requiere una buena controladora y motores en buen estado, revisar en los primeros vuelos que los motores no se calienten)

set iterm_relax_cutoff = 30  
set rc_smoothing_auto_smoothness = 5  
set ff_interpolate_sp = ON  
set ff_smooth_factor = 0  
set ff_spike_limit = 60  
set ff_boost = 20  
set feedforward_transition = 0  
set yaw_lowpass_hz = 100  
set throttle_boost = 7  
set throttle_boost_cutoff = 25  
set dyn_lpf_dterm_curve_expo = 7  
set gyro_rpm_notch_q = 600  

- Race y Fast Freestyle (Tolera controladoras de gama media, quad de respuesta rapida)

set iterm_relax_cutoff = 20  
set rc_smoothing_auto_smoothness = 7  
set ff_interpolate_sp = AVERAGED_2  
set ff_smooth_factor = 20  
set ff_spike_limit = 70  
set ff_boost = 15  
set feedforward_transition = 0  
set yaw_lowpass_hz = 100  
set throttle_boost = 7  
set throttle_boost_cutoff = 25  
set dyn_lpf_dterm_curve_expo = 7  
set gyro_rpm_notch_q = 700  

- HD (Ideal para hacer grabaciones en HD con nuestra camara de acción)

set iterm_relax_cutoff = 10  
set rc_smoothing_auto_smoothness = 20  
set ff_interpolate_sp = AVERAGED_3  
set ff_smooth_factor = 40  
set ff_spike_limit = 55  
set ff_boost = 0  
set feedforward_transition = 40  
set yaw_lowpass_hz = 70  
set throttle_boost = 5  
set throttle_boost_cutoff = 10  
set dyn_lpf_dterm_curve_expo = 7  
set gyro_rpm_notch_q = 800  

- Cinematic (Ideal para cinehoops y hoops)

set iterm_relax_cutoff = 5  
set rc_smoothing_auto_smoothness = 40  
set ff_interpolate_sp = AVERAGED_4  
set ff_smooth_factor = 50  
set ff_spike_limit = 50  
set ff_boost = 0  
set feedforward_transition = 70  
set yaw_lowpass_hz = 50  
set throttle_boost = 2  
set throttle_boost_cutoff = 10  
set dyn_lpf_dterm_curve_expo = 8  
set gyro_rpm_notch_q = 900  
set iterm_windup = 75  

- Valores por defecto ( Valor zero sisgnifica 'apagado')  
Estos son los valores por defecto por si queremos volver atrás en alguna de estas configuraciones

set iterm_relax_cutoff = 15  
set rc_smoothing_auto_smoothness = 10  
set ff_interpolate_sp = AVERAGED_2  
set ff_smooth_factor = 37	  
set ff_spike_limit = 60  
set ff_boost = 15  
set feedforward_transition = 0  
set yaw_lowpass_hz = 0  
set throttle_boost = 5  
set throttle_boost_cutoff = 15  
set dyn_lpf_dterm_curve_expo = 5  
set gyro_rpm_notch_q = 500  
set iterm_windup = 100  

- Configuración extra para los usuarios de 4in1  
Recomendable si usas un 4in1 usar estos ajustes independientemente del modo de vuelo seleccionado anteriormente

set dyn_lpf_dterm_curve_expo = 6  
set vbat_sag_compensation = 100  
set vbat_pid_gain = OFF  
set rc_smoothing_type = FILTER  
set rc_smoothing_input_hz = 0  
set rc_smoothing_derivative_hz = 0  
set rc_smoothing_input_type = BIQUAD  
set rc_smoothing_derivative_type = PT1  
set rc_smoothing_auto_smoothness = 10  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/Filtros.PNG">

Es muy recomendable en esta pestaña editar los valores del **Filtro Notch Dinámico** situado en la parte inferior izquierda.  
Los valores recomdendados y provados por Joshua Bradwell son los que aparecen en la imagen.  
Giro Filtro Notch Dinámico Ancho = 0  
Giro Filtro Notch Dinámico Q =250   
Giro Filtro Notch Dinámico Min =70   
Giro Filtro Notch Dinámico Max =350   

Además, los valores multiplicadores **Filtro Giro** y **Filtro D Term** se pueden mover un poco para filtrar menos la señal que enviamos a nuestro quad y tener una respuesta mas rapida. Hay que mover los dos por igual.  

Personalmente he provado el valor **1.2 en ambos**, si provais alguno y no os convence volver a el valor por defecto 1 en ambos.
