/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_atoi.c                                          :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: yiwzhang <yiwzhang@student.42.fr>          +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2018/04/18 20:56:12 by yiwzhang          #+#    #+#             */
/*   Updated: 2018/04/18 09:29:25 by yiwzhang         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include "libft.h"

int		ft_atoi(const char *str)
{
	int		sign;
	long	r;

	r = 0;
	sign = 1;
	while (*str == ' ' || (*str >= 9 && *str <= 13))
		str++;
	if (*str == '-')
	{
		sign = -1;
		str++;
		if (*str == '+')
			return (0);
	}
	else if (*str == '+')
		str++;
	while (*str >= '0' && *str <= '9')
	{
		r = r * 10 + *str - '0';
		str++;
	}
	return (sign * (int)r);
}
