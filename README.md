define Input_Interval = 50; // 50ms para old gen

init {
    // Ajuste para cruce de plataforma en Playstation al cargar
    if((get_console() == PIO_PS5 || get_console() == PIO_PS4) && get_controller() != PIO_PS5 && get_controller() != PIO_PS4) {
        INTERACTION_MENU = PS4_TOUCH;}}main {
    // Activa el sticky aim assist en tercera persona al mantener presionado L2
    if(get_val(PS4_L2)) {
        combo_run(Sticky_Aim_Assist);}}combo Sticky_Aim_Assist {
    // Simula movimientos suaves en el joystick derecho para asistencia de apuntado
    set_val(PS4_RX, 12); // Movimiento leve hacia la derecha
    wait(Input_Interval);    set_val(PS4_RX, -12); // Movimiento 
    wait(Input_Interval);    set_val(PS4_RY, 8); // Movimiento 
    wait(Input_Interval);    set_val(PS4_RY, -8); // Movimiento ú»ˆ±…µµ…³±†¶†³
