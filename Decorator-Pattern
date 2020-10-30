using System;
using System.Collections.Generic;
using System.Text;

namespace Design_Pattern
{
    public abstract class IceCream
    {
        string baseType;
        string icecream;

        protected IceCream(string BaseType, string Icecream)
        {
            this.baseType = BaseType;
            this.icecream = Icecream;
        }
        public abstract int getCost();

        public string GetDescription()
        {
            return (baseType + " " + icecream);
        }

    }

    public abstract class IceCreamDecorator : IceCream
    {
        protected IceCreamDecorator(string BaseType, string Icecream) : base(BaseType, Icecream)
        {
        }

        public abstract string GetDescription();
    }
    public class ConeIceCream : IceCream
    {
        public ConeIceCream(string BaseType, string Icecream):base(BaseType, Icecream)
        {
                
        }

        public override int getCost()
        {
            return 20; 
        }
    }

    public class CupIceCream : IceCream
    {
        public CupIceCream(string BaseType, string Icecream):base(BaseType,Icecream)
        {

        }
        public override int getCost()
        {
            return 10;
        }
    }

    public class ChocolateCone : IceCreamDecorator
    {
        IceCream iceCream;
        public ChocolateCone(IceCream iceCream):base(string.Empty,string.Empty)
        {
            this.iceCream = iceCream;       
        }
        public override int getCost()
        {
            return this.iceCream.getCost() + 20;
        }

        public override string GetDescription()
        {
            return "Chocolate " + this.iceCream.GetDescription();
        }
    }

    public class fruitAndNutTopping:IceCreamDecorator
    {
        IceCream iceCream;
        public fruitAndNutTopping(IceCream iceCream) : base(string.Empty, string.Empty)
        {
            this.iceCream = iceCream;
        }
        public override int getCost()
        {
            return this.iceCream.getCost() + 20;
        }

        public override string GetDescription()
        {
            return this.iceCream.GetDescription()+"With Fruit and Nut Topping";
        }
    }


    public class IceCreamStore
    {
        public static void Main()
        {
            IceCream iceCream = new fruitAndNutTopping( new ChocolateCone(new ConeIceCream("Cone", "Vanilla")));
            Console.WriteLine(iceCream.GetDescription() + "Costs:" + iceCream.getCost());

        }
    }
}
