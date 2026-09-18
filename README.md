# Tamonnikov_Nikita_IKBO-70-25

# Task_1
localhost:/etc# cut -d: -f1 passwd | sort

# Task_2
localhost:/etc# awk '!/^#/ && NF {print $2, $1}' protocols | sort -rn | head -5
