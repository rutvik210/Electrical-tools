#!/bin/bash

echo "=== Ohm's Law Calculator ==="
echo "Choose what you want to calculate:"
echo "1. Voltage (V = I * R)"
echo "2. Current (I = V / R)"
echo "3. Resistance (R = V / I)"
read -p "Enter choice [1-3]: " choice

case $choice in
  1)
    read -p "Enter Current (I) in Amps: " I
    read -p "Enter Resistance (R) in Ohms: " R
    V=$(echo "$I * $R" | bc -l)
    echo "Voltage (V) = $V Volts"
    ;;
  2)
    read -p "Enter Voltage (V) in Volts: " V
    read -p "Enter Resistance (R) in Ohms: " R
    I=$(echo "$V / $R" | bc -l)
    echo "Current (I) = $I Amps"
    ;;
  3)
    read -p "Enter Voltage (V) in Volts: " V
    read -p "Enter Current (I) in Amps: " I
    R=$(echo "$V / $I" | bc -l)
    echo "Resistance (R) = $R Ohms"
    ;;
  *)
    echo "Invalid choice"
    ;;
esac
