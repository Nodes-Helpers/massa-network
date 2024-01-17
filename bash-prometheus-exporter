#!/bin/sh

cd /root/massa/massa-client
wallet_info=$(./massa-client -p YOUR_PASSWORD_HERE wallet_info)
get_addresses=$(./massa-client -p YOUR_PASSWORD_HERE get_addresses YOUR_ADDRESS_HERE)
get_status=$(./massa-client -p YOUR_PASSWORD_HERE get_status)

wallet_info_result=$(echo "$wallet_info" | grep -oP "Balance: final=\K[0-9.]+(?=, candidate)")
echo "wallet_balance $wallet_info_result"

wallet_active_rolls=$(echo "$wallet_info" | grep -oP "Rolls: active=\K[0-9.]+(?=, final)")
echo "wallet_active_rolls $wallet_active_rolls"

last_cycle_blocks=$(echo "$get_addresses" | grep -oP "Cycle \d+ \(candidate\): produced \d+ and missed \d+ blocks with \d+ active rolls")
#echo "$last_cycle_blocks"
produced_blocks=$(echo "$last_cycle_blocks" | grep -oP "produced \K\d+")
echo "produced_blocks_last_cycle $produced_blocks"

missed_blocks=$(echo "$last_cycle_blocks" | grep -oP "missed \K\d+")
echo "missed_blocks_last_cycle $missed_blocks"

current_cycle=$(echo "$last_cycle_blocks" | grep -oP "Cycle \K\d+")
echo "current_cycle $current_cycle"

block_reward=$(echo "$get_status" | grep -oP "Block reward: \K[0-9.]+(?=)")
echo "block_reward $block_reward"

in_connections=$(echo "$get_status" | grep -oP "In connections: \K\d+")
echo "in_connections $in_connections"

out_connections=$(echo "$get_status" | grep -oP "Out connections: \K\d+")
echo "out_connections $out_connections"

last_cycles=$(echo "$get_addresses" | grep -Eo "Cycle [0-9]+ \(.*\): produced [0-9]+ and missed [0-9]+ blocks( with [0-9]+ active rolls)?")
cycle_numbers=$(echo "$last_cycles" | grep -Po "Cycle \K\d+")
number1=$(echo "$cycle_numbers" | sed -n 1p)
number2=$(echo "$cycle_numbers" | sed -n 2p)
number3=$(echo "$cycle_numbers" | sed -n 3p)
number4=$(echo "$cycle_numbers" | sed -n 4p)
number5=$(echo "$cycle_numbers" | sed -n 5p)
number6=$(echo "$cycle_numbers" | sed -n 6p)
number7=$(echo "$cycle_numbers" | sed -n 7p)

echo "number_first_cycle $number1"
echo "number_second_cycle $number2"
echo "number_third_cycle $number3"
echo "number_fourth_cycle $number4"
echo "number_fifth_cycle $number5"
echo "number_sixth_cycle $number6"
echo "number_seventh_cycle $number7"

produced_numbers=$(echo "$get_addresses" | grep -Po "produced \K\d+")
produced_number1=$(echo "$produced_numbers" | sed -n 1p)
produced_number2=$(echo "$produced_numbers" | sed -n 2p)
produced_number3=$(echo "$produced_numbers" | sed -n 3p)
produced_number4=$(echo "$produced_numbers" | sed -n 4p)
produced_number5=$(echo "$produced_numbers" | sed -n 5p)
produced_number6=$(echo "$produced_numbers" | sed -n 6p)
produced_number7=$(echo "$produced_numbers" | sed -n 7p)

echo "number_produced_first_cycle $produced_number1"
echo "number_produced_second_cycle $produced_number2"
echo "number_produced_third_cycle $produced_number3"
echo "number_produced_fourth_cycle $produced_number4"
echo "number_produced_fifth_cycle $produced_number5"
echo "number_produced_sixth_cycle $produced_number6"
echo "number_produced_seventh_cycle $produced_number7"

missed_numbers=$(echo "$get_addresses" | grep -Po "missed \K\d+")
missed_number1=$(echo "$missed_numbers" | sed -n 1p)
missed_number2=$(echo "$missed_numbers" | sed -n 2p)
missed_number3=$(echo "$missed_numbers" | sed -n 3p)
missed_number4=$(echo "$missed_numbers" | sed -n 4p)
missed_number5=$(echo "$missed_numbers" | sed -n 5p)
missed_number6=$(echo "$missed_numbers" | sed -n 6p)
missed_number7=$(echo "$missed_numbers" | sed -n 7p)

echo "number_missed_first_cycle $missed_number1"
echo "number_missed_second_cycle $missed_number2"
echo "number_missed_third_cycle $missed_number3"
echo "number_missed_fourth_cycle $missed_number4"
echo "number_missed_fifth_cycle $missed_number5"
echo "number_missed_sixth_cycle $missed_number6"
echo "number_missed_seventh_cycle $missed_number7"
