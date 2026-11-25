# Estatus 5S · CDD Bávaro

Dashboard de 5S (anual, mensual y por evaluación): https://jerez129.github.io/5sPages/

- Se actualiza cargando los Excel del reporte 5S (hojas "Mes actual Ejecutado" e "Historico Ejecutado"). Se pueden cargar varios a la vez; las evaluaciones repetidas se cuentan una sola vez.
- Los datos se guardan en la base D1 `owd-db` (tabla `s5_evals`) a través del Worker `owd-api` (`/api/5s`). Para guardar se pide la misma clave de edición del tablero OWD.
- Cálculo: la nota de cada S es la suma de "Ponderación (%)" de sus preguntas; la nota de una evaluación es el promedio de sus S; los totales promedian evaluaciones. Meta: 80 % (verde), 60–79 % en riesgo, menos de 60 % bajo.
- Cumplimiento del plan mensual: evaluaciones hechas (hasta lo planificado por subárea) ÷ planificadas. El plan se edita en el botón "Plan mensual" y se guarda en la base (config `s5_plan`). Plan base: 40 al mes (Almacén 8, Oficinas 10, Camión 22).
